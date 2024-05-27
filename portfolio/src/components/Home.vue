<template>
  <div class="home">
    <section id="home">
      <h1>Mon Portfolio</h1>
      <p>
        Bienvenue sur mon portfolio. Découvrez mon expérience, mes projets et n'hésitez pas à me contacter.
      </p>
    </section>
    <div class="stars-container" ref="starsContainer"></div> <!-- Section pour les étoiles -->
  </div>
</template>

<script>
export default {
  name: 'Home',
  mounted() {
    this.createStars();
    setInterval(this.shineStar, 1000);
  },
  methods: {
    createStars() {
      const starContainer = this.$refs.starsContainer;
      const stars = [];
      const starSizes = [
        { class: "small", size: 3 },
        { class: "medium", size: 5 },
        { class: "large", size: 7 }
      ];

      for (let i = 0; i < 30; i++) {
        const star = document.createElement("div");
        star.classList.add("star");

        const randomSize = starSizes[Math.floor(Math.random() * starSizes.length)];
        star.classList.add(randomSize.class);
        star.style.width = `${randomSize.size}px`;
        star.style.height = `${randomSize.size}px`;
        star.style.backgroundColor = '#FFD700'; // Couleur jaune
        star.style.opacity = '0'; // Initialement invisible
        star.style.transition = 'opacity 0.8s ease-in-out'; // Transition d'opacité

        const randomX = Math.random() * 100;
        const randomY = Math.random() * 100;
        star.style.left = `${randomX}%`;
        star.style.top = `${randomY}%`;
        star.style.position = `absolute`;

        starContainer.appendChild(star);
        stars.push(star);
      }

      this.stars = stars;
    },
    shineStar() {
      const numStars = Math.floor(Math.random() * this.stars.length) + 1;
      const starIndices = [];

      while (starIndices.length < numStars) {
        const randomIndex = Math.floor(Math.random() * this.stars.length);
        if (!starIndices.includes(randomIndex)) {
          starIndices.push(randomIndex);
          const star = this.stars[randomIndex];
          star.style.opacity = star.style.opacity === '0' ? '1' : '0';
        }
      }
    }
  },
  data() {
    return {
      stars: []
    };
  }
};
</script>

<style scoped>
.home {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
  color: white;
  text-align: center;
  margin-top: 150px;
}

#home {
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.stars-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none; /* Permet de rendre les étoiles transparentes aux événements de la souris */
  overflow: hidden; /* Assure que les étoiles ne débordent pas de la page */
}
</style>
