<script setup>

</script>

<template>
    <div id="skills">
      <h2 class="text-highlight-1 section-title"> Mes Technos</h2>
      <div id="icons-list">
        <div class="tech-container">
          <i class="tech-icon devicon-html5-plain colored"></i><br/> <span>HTML5</span>
        </div>

        <div class="tech-container">
          <i class="tech-icon devicon-css3-plain colored"></i><br/><span>CSS</span>
        </div>

        <div class="tech-container">
          <i class="tech-icon devicon-javascript-plain colored"></i><br/><span>JavaScript</span>
        </div>

        <div class="tech-container">
          <i class="tech-icon devicon-nodejs-plain colored"></i><br/><span>Node.Js</span>
        </div>

        <div class="tech-container">
          <i class="tech-icon devicon-vuejs-plain colored"></i><br/><span>Vue.Js</span>
        </div>

        <div class="tech-container">
          <i class="tech-icon devicon-laravel-original colored"></i><br/><span>Laravel</span>
        </div>

        <div class="tech-container">
          <i class="tech-icon devicon-python-plain  colored"></i><br/><span>Python</span>
        </div>
        <div class="tech-container">
          <i class="tech-icon devicon-java-plain  colored"></i><br/><span>Java</span>
        </div>
        <div class="tech-container">
          <i class="tech-icon devicon-quarkus-plain  colored"></i><br/><span>Quarkus</span>
        </div>
        <div class="tech-container">
          <i class="tech-icon devicon-ktor-plain  colored"></i><br/><span>Ktor</span>
        </div>
        <div class="tech-container">
          <i class="tech-icon devicon-react-original  colored"></i><br/><span>React Js</span>
        </div>
        <div class="tech-container">
          <i class="tech-icon devicon-git-plain  colored"></i><br/><span>Git</span>
        </div>
        <div class="tech-container">
          <i class="tech-icon devicon-gitlab-plain colored"></i><br/><span>Gitlab</span>
        </div>

      </div>
    </div>
</template>

<style scoped>
  #skills {
    margin-top:60px
  }

  #icons-list{
    display:grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    grid-column-gap: 5px;
    grid-row-gap: 50px;
    margin-top: 35px;
  }

  .tech-container {
    text-align: center;
    color:var(--vt-c-custom-text-1);
    transition: transform 0.5s
  }
  .tech-container span {
    font-weight: bold;
  }

  .tech-container:hover {
    transform: rotate(15deg);
    color:var(--vt-c-custom-text-2);
  }

  .tech-icon{
    font-size: 80px;
    margin: 0 auto;
    color:var(--vt-c-custom-text-1);
  }

  .tech-icon:hover{
    color:var(--vt-c-custom-text-2);
    transform: rotate(15deg)
  }



</style>