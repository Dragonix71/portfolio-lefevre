<template>
  <div class="base-layout">
    <header>
      <!-- Menu déroulant -->
      <div class="dropdown" @mouseleave="closeDropdown">
        <button class="dropbtn" @click="toggleDropdown">
          <img class="img-menu" src="../assets/menu.png" alt="Menu" />
        </button>
        <div class="dropdown-content" ref="dropdownContent">
          <router-link to="/">Home</router-link>
          <router-link to="/about">About</router-link>
          <router-link to="/project">Project</router-link>
          <router-link to="/contact">Contact</router-link>
        </div>
      </div>
    </header>
    <main>
      <router-view></router-view>
    </main>
    <footer>
      <p>© 2024 Mon Portfolio. Tous droits réservés.</p>
    </footer>
    <BackToTop />
  </div>
</template>

<script>
import BackToTop from './BackToTop.vue';

export default {
  name: 'BaseLayout',
  components: {
    BackToTop
  },
  methods: {
    toggleDropdown() {
      const dropdownContent = this.$refs.dropdownContent;
      if (dropdownContent.style.maxHeight === '0px' || dropdownContent.style.maxHeight === '') {
        dropdownContent.style.maxHeight = `${dropdownContent.scrollHeight}px`;
      } else {
        dropdownContent.style.maxHeight = '0px';
      }
    },
    closeDropdown() {
      const dropdownContent = this.$refs.dropdownContent;
      dropdownContent.style.maxHeight = '0px';
    }
  }
};
</script>

<style scoped>
.base-layout {
  display: flex;
  flex-direction: column;
  min-height: 100%;
  font-family: Arial, sans-serif;
}

header {
  color: white;
  padding: 50px;
  display: flex;
  justify-content: flex-end; /* Aligner à droite */
  align-items: center;
  margin: 25px;
}

.img-menu {
  width: 50px;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropbtn {
  background: none;
  border: none;
  color: black;
  cursor: pointer;
  font-size: 16px;
  text-align: right; /* Texte aligné à droite */
}

.dropdown-content {
  display: block; /* Toujours affiché pour permettre la transition */
  position: absolute;
  background-color: transparent;
  min-width: 160px;
  box-shadow: none;
  right: 0;
  z-index: 1;
  text-align: right; /* Texte aligné à droite */
  transition: max-height 0.3s ease-in-out;
  overflow: hidden;
  max-height: 0;
  font-size: 18px;
}

.dropdown-content a {
  color: black;
  text-decoration: none;
  display: block;
  text-align: right; /* Texte aligné à droite */
  margin-top: 25px;
  margin-right: 6px;
}

main {
  flex: 1;
  padding: 1rem;
}

footer {
  background: #333;
  color: white;
  padding: 2px;
  text-align: center;
}
</style>
