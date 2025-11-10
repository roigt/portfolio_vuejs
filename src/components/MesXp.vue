<script setup>
   import {ref} from 'vue'

   let activeBloc = ref(0);
   let experiences = ref([
     {
       title: "Assistant Développeur Intégrateur",
       company: "Bassetti Group",
       location: "Grenoble",
       date: "Avril 2025 - Septembre 2025",
       line1: "Participation au développement et à l’intégration d’outils internes basés sur TEEXMA ",
       line2: "Mise en place de flux automatisés via Node-RED, Make, Zapier et Mendix.",
       line3: "Collaboration avec des équipes R&D pour l’amélioration continue des solutions techniques.",
       technologies: "JavaScript, Node.js, Vue.js, Node-RED, Make, Mendix, Windmill"
     },
     {
       title: "Stagiaire Développeur FullStack",
       company: "Centre de Recherche Informatique de Lens",
       location: "Lens",
       date: "Avril 2024 - Juin 2024",
       line1: "Conception d’un outil d’affichage de procès-verbaux de jury selon l’approche par blocs de compétences.",
       line2: "Mise en place d’une architecture modulaire et maintenance évolutive du système.",
       line3: "Travail collaboratif avec Git et GitLab pour le suivi du projet.",
       technologies: "JavaScript, HTML, CSS, XML, Git, GitLab"
     },
     {
       title: "Stagiaire Développeur FullStack",
       company: "StudentBank",
       location: "Arras",
       date: "Avril 2023 - Juin 2023",
       line1: "Développement d’une application web de location de logements et services financiers pour étudiants.",
       line2: "Intégration du front React avec un backend PHP/MySQL.",
       line3: "Mise en œuvre du design responsive et gestion des données via API REST.",
       technologies: "React.js, PHP, MySQL, HTML5, CSS3, JavaScript"
     },
     {
       title: "Stagiaire Administrateur Systèmes & Réseaux",
       company: "SGE & SoftSolux",
       location: "Lomé",
       date: "Juin 2021 - Août 2022",
       line1: "Mise en place et administration d’un serveur NAS avec haute disponibilité (DRBD, HeartBeat, HA Proxy).",
       line2: "Maintenance du parc informatique et configuration des postes utilisateurs.",
       line3: "Simulation du réseau d’entreprise avec GNS3 et sauvegardes avec Veeam Backup.",
       technologies: "Linux, Ubuntu Server, DRBD, HA Proxy, GNS3, Veeam Backup"
     }
   ]);

   const ShowXp =(id)=>{
     activeBloc.value=id;
   }
</script>

<template>
   <div id="xp">
     <h2 class="text-highlight-1 section-title"> Expériences</h2>
     <div id="left">
       <p :class="activeBloc ===0 ? 'active':''" class="company fw600" @click="ShowXp(0)">Bassetti Group</p>
       <p :class="activeBloc ===1 ? 'active':''" class="company fw600" @click="ShowXp(1)">CERI de Lens</p>
       <p :class="activeBloc ===2 ? 'active':''" class="company fw600" @click="ShowXp(2)">StudentBank</p>
       <p :class="activeBloc ===3 ? 'active':''" class="company fw600" @click="ShowXp(3)">SGE</p>
     </div>
     <div id="right">
       <template v-for="(job,index) in experiences">
          <div class="job-details" :class="index ===activeBloc?'':'hide'" :id="'bloc_'+index">
            <h3 class="fw600">{{job.title}}</h3>
            <span id="date">{{job.date}}</span>
            <br/>
            <p class="fw600 mtb8 " style="margin-top: 10px">
              Stack technique:  {{job.technologies}}
            </p>
            <p class="fw600 mtb8 " style="margin-top: 10px">
              {{job.line1}}
            </p>
            <p class="fw600 mtb8 " style="margin-top: 10px">
              {{job.line2}}
            </p>
            <p class="fw600 mtb8 " style="margin-top: 10px">
              {{job.line3}}
            </p>


          </div>
       </template>
     </div>
   </div>
</template>

<style scoped>
  #xp{
    margin-top: 60px;
    margin-bottom: 200px;
  }
  #xp #left{
    float:left;
    width: 25%;
  }
  #xp #right{
    float: left;
    width: 75%;
  }

  #xp #right h3{
    font-size: 20px;
  }

  .fw600{
    font-weight: 600;
    color: white;
  }

  .mtb8{
    margin: 8px 0px
  }

  #date{
    font-style: italic;
    font-size: 14px;
  }

  .company{
    margin-top: 15px;
    border-left: 8px solid var(--vt-c-custom-text-1);
    border-radius: 15px ;
    line-height: 30px;
    padding-left: 10px;
  }

  .active{
    border-left: 8px solid var(--vt-c-custom-text-2);
    color: var(--vt-c-custom-text-2);
    border-radius: 10px ;
  }

  .company:hover{
    cursor:pointer;
    color: var(--vt-c-custom-text-1)
  }

  .hide{
    display: none;
  }

  @media screen and (max-width: 600px){
    #xp #right{
      width: 100%;
      margin-top: 20px;
    }

    #xp #left{
      width: 100%;
    }

    .company{
      border: none;
      padding-left: 0px;
      float: left;
      margin-right: 10px;
    }
  }

</style>