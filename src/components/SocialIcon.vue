<script setup>
  const props = defineProps({
    icon: String,
    link: String,
    alt: String,
  })
</script>

<template>
  <a :href="link" target="_blank">
     <img  :src="`/icons/${props.icon}.png`" :alt="alt"  class="social-icon" />
  </a>


</template>

<style scoped>
  .social-icon{
    background-color:whitesmoke;
    margin: 20px;
    border-radius: 40%; /* rond si c’est un portrait */
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }


  .social-icon:hover{
    transform: scale(1.05);
    box-shadow: 0 2px 2px #00d1ff;
  }
</style>