<script setup>

</script>

<template>
   <div id="projects">
     <h2 class="text-highlight-1 section-title" > Mes Projets</h2>
     <ul>
       <li style="--accent-color:#41516C">
         <img src="../assets/laravel-technews2.png" style="width: 100%; height: 200px"/>
         <div class="date">2025</div>
         <div class="title">Tech news</div>
         <div class="descr">
           <p>Lien : <a href="https://technews-app-main-rrhpdo.laravel.cloud/" class="custom-link" target="_blank" rel="noopener noreferrer">Technews</a></p>
           Technologies:  <p style="color: yellow">Laravel , Blade, MySQL, Breeze</p>
         </div>
       </li>
       <li style="--accent-color:#FBCA3E">
         <img src="../assets/Ktor-lib.png" style="width: 100%; height: 200px"/>
         <div class="date">2025</div>
         <div class="title">Library Manager</div>
         <div class="descr">
           <p>Lien github: <a href="https://github.com/roigt/App_gestion_biblioth-que_en_Ktor" class="custom-link">Ktor Library Manager</a></p>

           Technologies:  <p style="color: yellow">Ktor (Kotlin), HTML, CSS, PostgreSQL, Docker</p>
         </div>
       </li>
       <li style="--accent-color:#E24A68">
         <img src="../assets/quarkus2.png" style="width: 100%; height: 200px"/>
         <div class="date">2025</div>
         <div class="title">Fammeal</div>
         <div class="descr">
           <p>Lien github: <a href="https://github.com/roigt/fammeal_backend" class="custom-link">Fammeal</a></p>
           Technologies:  <p style="color: yellow">Quarkus (Java), PostgreSQL,Docker, Ngrok, Ethereal,Cloudinary</p>
         </div>
       </li>
       <li style="--accent-color:#1B5F8C">
         <img src="../assets/annuaire-react.png" style="width: 100%; height: 200px"/>
         <div class="date">2024</div>
         <div class="title">Annuaire des administrations du pays de la loire</div>
         <div class="descr">
           <p>Lien: <a href="https://roigt.github.io/annuaire" class="custom-link">annuaire</a></p>
           <p>Lien github: <a href="https://github.com/roigt/annuaire/" class="custom-link">Annuaire des administrations du pays de la loire</a></p>
           Technologies:  <p style="color: yellow">React Js , JavaScript</p>
         </div>
       </li>
       <li style="--accent-color:#4CADAD">
         <img src="../assets/pokemon-logo.png" style="width: 100%; height: 200px"/>
         <div class="date">2024</div>
         <div class="title">Pokemon API REST</div>
         <div class="descr">
           <p>Lien github: <a href="https://github.com/roigt/node-api-pokemon" class="custom-link">node-api-pokemon</a></p>
           Technologies:  <p style="color: yellow">JavaScript, Node JS, Sequelize(ORM), MySQL</p>
         </div>
       </li>
     </ul>
   </div>

</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap");

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  --color: transparent;
  --bgColor: rgba(245, 245, 245);
  min-height: 100vh;
  display: grid;
  align-content: center;
  gap: 2rem;
  padding: 2rem;
  font-family: "Poppins", sans-serif;
  color: var(--color);
  background: var(--bgColor);
}
#projects{
  margin-top: 50px;
}

h1 {
  text-align: center;
}

ul {
  --col-gap: 2rem;
  --row-gap: 2rem;
  --line-w: 0.25rem;
  display: grid;
  grid-template-columns: var(--line-w) 1fr;
  grid-auto-columns: max-content;
  column-gap: var(--col-gap);
  list-style: none;
  width: min(60rem, 90%);
  margin-inline: auto;
}

/* line */
ul::before {
  content: "";
  grid-column: 1;
  grid-row: 1 / span 20;
  background: rgb(225, 225, 225);
  border-radius: calc(var(--line-w) / 2);
}

/* columns*/

/* row gaps */
ul li:not(:last-child) {
  margin-bottom: var(--row-gap);
}

/* card */
ul li {
  grid-column: 2;
  --inlineP: 1.5rem;
  margin-inline: var(--inlineP);
  grid-row: span 2;
  display: grid;
  grid-template-rows: min-content min-content min-content;
  background-color: transparent;
  color: white;
  border-bottom: 1px solid white;
  border-left: 1px solid white;
  border-right: 1px solid white;
  padding: 10px; /* Un peu d’espace à l’intérieur */
  border-radius: 6px; /* Coins arrondis, optionnel */
  margin-top: 25px;
}
ul li:hover {
  transform: scale(1.05); /* Zoom léger */
  background-color: transparent; /* Légère surbrillance */
}

/* date */
ul li .date {
  --dateH: 3rem;
  height: var(--dateH);
  margin-inline: calc(var(--inlineP) * -1);

  text-align: center;
  background-color: var(--accent-color);

  color: white;
  font-size: 1.25rem;
  font-weight: 700;

  display: grid;
  place-content: center;
  position: relative;

  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
}

/* date flap */
ul li .date::before {
  content: "";
  width: var(--inlineP);
  aspect-ratio: 1;
  background: var(--accent-color);
  background-image: linear-gradient(rgba(0, 0, 0, 0.2) 100%, transparent);
  position: absolute;
  top: 100%;

  clip-path: polygon(0 0, 100% 0, 0 100%);
  right: 0;
}

/* circle */
ul li .date::after {
  content: "";
  position: absolute;
  width: 2rem;
  aspect-ratio: 1;
  background: var(--bgColor);
  border: 0.3rem solid var(--accent-color);
  border-radius: 50%;
  top: 50%;

  transform: translate(50%, -50%);
  right: calc(100% + var(--col-gap) + var(--line-w) / 2);
}

/* title descr */
ul li .title,
ul li .descr {
  background: var(--bgColor);
  position: relative;
  padding-inline: 1.5rem;
}
ul li .title {
  overflow: hidden;
  padding-block-start: 1.5rem;
  padding-block-end: 1rem;
  font-weight: 500;
}
ul li .descr {
  padding-block-end: 1.5rem;
  font-weight: 300;
}

/* shadows */
ul li .title::before,
ul li .descr::before {
  content: "";
  position: absolute;
  width: 90%;
  height: 0.5rem;
  background:whitesmoke;
  left: 50%;
  border-radius: 50%;
  filter: blur(4px);
  transform: translate(-50%, 50%);
}
ul li .title::before {
  bottom: calc(100% + 0.125rem);
}

ul li .descr::before {
  z-index: -1;
  bottom: 0.25rem;
}

@media (min-width: 40rem) {
  ul {
    grid-template-columns: 1fr var(--line-w) 1fr;
  }
  ul::before {
    grid-column: 2;
  }
  ul li:nth-child(odd) {
    grid-column: 1;
  }
  ul li:nth-child(even) {
    grid-column: 3;
  }

  /* start second card */
  ul li:nth-child(2) {
    grid-row: 2/4;
  }

  ul li:nth-child(odd) .date::before {
    clip-path: polygon(0 0, 100% 0, 100% 100%);
    left: 0;
  }

  ul li:nth-child(odd) .date::after {
    transform: translate(-50%, -50%);
    left: calc(100% + var(--col-gap) + var(--line-w) / 2);
  }
  ul li:nth-child(odd) .date {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
  }
}

.credits {
  margin-top: 1rem;
  text-align: right;
}
.credits a {
  color: var(--color);
}

.custom-link {
  color: #fff; /* couleur blanche */
  text-decoration: none; /* supprime le soulignement */
  font-weight: 500;
  transition: all 0.3s ease;
}

.custom-link:hover {
  color: #00d1ff; /* effet couleur au survol */
  text-decoration: underline; /* optionnel : souligne au survol */
}


</style>