<script setup>
  import {ref} from 'vue'
  import ProjectSingle from "@/components/ProjectSingle.vue";


  let projects = ref([
    {
      name:"Le projet N 1",
      image:"projet.png",
      tags:"VueJs,PHP,HTML",
      description:"qsdchhs sdcqdscs sdcqsdc",
      tasks:"qsdcsdcsqscds sdcqdss sdcq sdcqsd c"
    },
    {

      name:"Le projet N 2",
      image:"projet.png",
      tags:"ReactJs,NodeJs,HTML",
      description:"qsdchhs sdcqdscs sdcqsdc",
      tasks:"qsdcsdcsqscds sdcqdss sdcq sdcqsd c"
    },
    {
      name:"Le projet N 3",
      image:"projet.png",
      tags:"React Native,Laravel,HTML",
      description:"qsdchhs sdcqdscs sdcqsdc",
      tasks:"qsdcsdcsqscds sdcqdss sdcq sdcqsd c"
    }

  ])
</script>

<template>
   <div id="projects">
     <h2 class="text-highlight-1 section-title">Quelques Projets</h2>
     <ProjectSingle v-for="(project,index) in projects" :key="project.name" :project="project" :reverse="index %2 ===0 ? false : true"/>
   </div>
</template>

<style scoped>
   #projects{
     display:inline-block;
     margin-top: 60px;
   }
</style>