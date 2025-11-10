<script setup>
  import {ref, onMounted,onUnmounted} from "vue";


  const props = defineProps({
    project:{
      type:Object,
      required:true
    },
    reverse:{
      type:Boolean,
      required:false
    }
  });

  let fadeInElements=ref();

  onMounted(()=>{
    fadeInElements.value=Array.from(document.getElementsByClassName('fade-in'));
    document.addEventListener('scroll',handleScroll);
  });

  onUnmounted(()=>{
    document.removeEventListener('scroll',handleScroll)
  });

  const handleScroll=()=>{
    for(let i=0; i<fadeInElements.value.length;i++){
      const elem= fadeInElements.value[i];
      if(isElemVisible(elem)){
        elem.style.opacity='1';
        elem.style.transform='scale(1)';
        fadeInElements.value.splice(i,1); //anim 1 fois
      }
    }
  }

  const isElemVisible =(el)=>{
    const rect = el.getBoundingClientRect();
    const elemTop= rect.top + 200;
    const elemBottom= rect.bottom;
    return elemTop < window.innerHeight && elemBottom >=0;
  }

  const getProjectTags=()=>{
    return props.project.tags.split(';');
  }

  const getProjectTasks=()=>{
    return props.project.tasks.split(';');
  }

</script>

<template>
  todo
</template>

<style scoped>

</style>