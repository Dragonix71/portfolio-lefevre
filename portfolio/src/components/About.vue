<template>
  <div class="about">
    <section id="about">
      <h1>À propos de moi</h1>
      <br/><br/>
      <p>
        Je suis un développeur web passionné avec une solide maîtrise du HTML, CSS et C#. J'ai acquis une expérience adaptée dans ces langages de programmation et je suis constamment en train d'apprendre et d'explorer de nouvelles technologies. J'ai une solide compréhension des principes fondamentaux du développement web, y compris la création de sites web esthétiquement plaisants.<br/><br/>
        En ce qui concerne le front-end, je suis à l'aise avec le HTML pour la structure du contenu, le CSS pour la mise en forme et la mise en page et également je suis capable de créer des mises en pages responsives.<br/><br/>
        En ce qui concerne le back-end, j'ai de bonnes compétences en programmation avec C#. Je suis capable de créer des applications Web robustes, de concevoir et de gérer des bases de données.<br/><br/>
        Je suis constamment motivé pour apprendre de nouvelles technologies et pour améliorer mes compétences en développement web.<br/><br/>
        Je suis ravi à l'idée de relever de nouveaux défis et de contribuer à des projets intéressants en tant que développeur web. Je suis toujours ouvert aux opportunités de collaboration et de développement professionnel.
      </p>
      <a href="/CV-LEFEVRE-Maxime.pdf" class="CV-button" download>Télécharger mon CV</a>
    </section>

    <section id="experience">
      <h2>Expériences</h2>
      <div class="experience-container">
        <div class="experience" v-for="(experience, index) in experiences" :key="index">
          <img class="experience-img" :src="experience.image" :alt="experience.title">
          <h3>{{ experience.title }}</h3>
          <p>{{ experience.description }}</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      experiences: [
        { 
          title: 'Mairie de Chalon', 
          description: "Lors de mon stage à la Mairie de Chalon, j'ai eu l'opportunité de travailler avec plusieurs équipes. J'ai été introduit aux bases du HTML par un développeur web, exploré les serveurs de la mairie avec l'administrateur système, et collaboré principalement avec l'équipe de maintenance informatique pour l'installation et la configuration de PC ainsi que l'installation de logiciels.",
          image: '/logo-chalon.png'
        },
        { 
          title: 'Escofier', 
          description: "Chez Escofier, j'ai assisté un automaticien dans le développement d'une interface homme-machine (IHM) pour les machines de l'usine. Cette expérience m'a permis de comprendre les besoins spécifiques en automatisation industrielle et de développer des compétences en conception d'interfaces utilisateur pour des environnements techniques.",
          image: '/logo-escofier.png'
        },
        { 
          title: 'Grand Chalon', 
          description: "Au Grand Chalon, j'ai aidé un développeur dans la refonte complète du site web avec WordPress. En parallèle, j'ai collaboré avec une graphiste pour créer des affiches destinées au site web à l'aide de Genially. Cette expérience m'a permis de développer des compétences en gestion de projets web et en conception graphique.",
          image: '/logo-grand-chalon.png'
        },
        { 
          title: 'Idéal Solutions', 
          description: "Chez Idéal Solutions, j'ai développé un site de e-commerce complet à partir de zéro pour soutenir le développement de leur entreprise. J'ai utilisé Vue.js pour le front-end et Node.js pour le back-end, créant une solution robuste et scalable. Cette expérience a renforcé mes compétences en développement full-stack.",
          image: '/logo-ideal-solutions.jpg'
        },
        { 
          title: 'Auto-Entrepreneur', 
          description: "En tant qu'auto-entrepreneur, j'ai continué à travailler en tant que prestataire informatique pour Idéal Solutions, afin de poursuivre le développement de leur site de e-commerce. Cette collaboration continue est un témoignage de la satisfaction de mes clients et de ma capacité à fournir des solutions techniques efficaces et adaptées.",
          image: '/logo-auto-entrepreneur.png'
        },
      ]
    };
  }
};
</script>

<style scoped>
.about {
  padding-left: 200px;
  padding-right: 200px;
  color: white;
}

#about {
  text-align: center;
}

#about h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

#about p {
  font-size: 1.2rem;
  line-height: 1.5;
  margin-bottom: 60px;
}

.CV-button {
  display: inline-block;
  padding: 10px 20px;
  font-size: 1.2rem;
  color: white;
  background-color: #007BFF;
  text-decoration: none;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.CV-button:hover {
  background-color: #0056b3;
}

#experience {
  text-align: center;
  margin-top: 60px;
}

#experience h2 {
  font-size: 2rem;
  margin-bottom: 20px;
}

.experience-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.experience {
  width: 45%; /* Assure que les expériences ont toujours la même largeur */
  margin: 10px;
  padding: 20px;
  text-align: center;
  border: 1px solid #ddd;
  border-radius: 10px;
  box-sizing: border-box;
}

.experience img {
  width: 25%;
  height: auto;
  border-radius: 10px;
  margin-bottom: 20px; /* Espace entre l'image et le titre */
}

.experience:nth-child(odd),
.experience:nth-child(even) {
  flex: 0 1 45%; /* Assure que les expériences prennent toujours 45% de la largeur disponible */
}

.experience h3 {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

.experience p {
  font-size: 1.2rem;
}
</style>
