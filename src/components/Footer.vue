<script setup>

import SocialIcon from "@/components/SocialIcon.vue";
</script>

<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-left">
        <h2>Julio Roigt</h2>
        <p>Développeur Full-Stack passionné, créant des expériences web modernes et performantes.</p>
      </div>

      <div class="footer-center">
        <h3>Navigation</h3>
        <ul>
          <li><a href="#about-me">À propos</a></li>
          <li><a href="#projects">Projets</a></li>
          <li><a href="#skills">Compétences</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>

      <div class="footer-right">
        <h3>Suivez-moi</h3>
        <div id="social-icons">
          <SocialIcon link="https://www.linkedin.com/in/julio-roigt-07b6071b4/" icon="linkedin" alt="linkedin "  id="icon" />
          <SocialIcon link="https://github.com/roigt" icon="github" alt=" github" id="icon"/>
        </div>
      </div>
    </div>

    <div class="footer-bottom">
      <p>© 2025 Julio Roigt — Tous droits réservés.</p>
    </div>
  </footer>



</template>

<style scoped>
.footer {
  background: linear-gradient(135deg, #0a0a23, #1c1c46);
  color: #fff;
  padding: 60px 20px 20px;
  font-family: 'Poppins', sans-serif;
  position: relative;
  margin-top: 50px;
}

.footer-container {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  max-width: 1100px;
  margin: auto;
  gap: 40px;
}

.footer-left h2 {
  font-size: 1.8rem;
  color: #00d1ff;
  margin-bottom: 10px;
}

.footer-left p {
  max-width: 350px;
  color: #dcdcdc;
  line-height: 1.6;
}

.footer-center h3,
.footer-right h3 {
  color: #00d1ff;
  margin-bottom: 15px;
  font-size: 1.2rem;
}

.footer-center ul {
  list-style: none;
  padding: 0;
}

.footer-center ul li {
  margin: 8px 0;
}

.footer-center ul li a {
  color: #dcdcdc;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-center ul li a:hover {
  color: #00d1ff;
}


.footer-bottom {
  text-align: center;
  margin-top: 40px;
  border-top: 1px solid rgba(255, 255, 255, 0.15);
  padding-top: 15px;
  font-size: 0.9rem;
  color: #aaa;
}

@media (max-width: 768px) {
  .footer-container {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .social-icons {
    justify-content: center;
  }
}

</style>