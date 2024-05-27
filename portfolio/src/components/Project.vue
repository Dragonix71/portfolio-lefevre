<template>
  <div class="project">
    <section id="project">
      <h1>Mes projets</h1>
      <div class="project-container">
        <div class="projects" v-for="(project, index) in projects" :key="index">
          <img :src="project.image" :alt="'Projet ' + (index + 1)">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Project',
  data() {
    return {
      projects: [
        { 
          image: '/projet-tyverne.png', 
          title: 'Tyverne.com', 
          description: "Tyverne était un projet visant à créer un wiki pour certaines fonctionnalités du jeu nommé Minecraft. Étant souvent sollicité pour des informations spécifiques sur ce jeu, j'ai décidé de créer un wiki pour partager ces connaissances. Le projet, bien que fonctionnel, a été abandonné relativement tôt et était développé en HTML et CSS simples." 
        },
        { 
          image: '/projet-studyevent.png', 
          title: 'StudyEvent', 
          description: "StudyEvent est un projet pour une association étudiante visant à transmettre des informations sur des événements étudiants. Je développe ce projet durant mon temps libre principalement pour le plaisir et pour expérimenter de nouvelles idées. Il est actuellement développé en HTML, CSS et JavaScript." 
        },
        { 
          image: '/projet-infotools.png', 
          title: 'Infotools', 
          description: "Infotools est un projet développé en C# durant ma deuxième année de BTS. Il permet une gestion complète des rendez-vous entre employés et clients, ainsi que des produits et des factures. Ce projet m'a permis de consolider mes compétences en programmation C# et en gestion de bases de données." 
        },
        { 
          image: '/projet-e-commerce.png', 
          title: 'E-commerce', 
          description: "Le site E-commerce est un projet développé en Vue.js et Node.js durant mon deuxième stage de BTS. J'ai continué à travailler sur ce projet en tant que prestataire informatique pour l'entreprise Idéal Solutions, afin de soutenir leur activité en ligne. Cette expérience m'a permis d'approfondir mes compétences en développement full-stack." 
        },
      ]
    };
  }
};
</script>

<style scoped>
.project {
  padding-left: 200px;
  padding-right: 200px;
  color: white; /* Texte en blanc */
}

#project {
  text-align: center;
  margin-top: 40px;
}

#project h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.project-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 50px;
}

.projects {
  width: 45%; /* Assure que les projets ont toujours la même largeur */
  margin: 10px;
  padding: 20px;
  text-align: center;
  border: 1px solid #ddd;
  border-radius: 10px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: center; /* Centre verticalement le contenu */
}

.project img {
  width: 100%;
  height: auto;
  border-radius: 10px;
  margin-bottom: 20px;
}

.project h3 {
  font-size: 1.5rem;
  margin-top: 10px;
}

.project p {
  font-size: 1.2rem;
  margin-top: 5px;
}
</style>
