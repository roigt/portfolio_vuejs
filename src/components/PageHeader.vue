<script setup>
import { ref } from "vue";

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
  <header class="header">
    <div class="header-container">
      <!-- Logo -->
      <h1 class="logo">Julio Roigt</h1>

      <!-- Navigation desktop -->
      <nav class="nav-desktop">
        <ul>
          <li><a href="#about-me">À propos</a></li>
          <li><a href="#skills">Compétences</a></li>
          <li><a href="#projects">Projets</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>

      <!-- Bouton burger -->
      <button class="burger" @click="toggleMenu" aria-label="Menu">
        <span :class="{ 'open': isMenuOpen }"></span>
      </button>
    </div>

    <!-- Menu mobile -->
    <nav class="nav-mobile" v-if="isMenuOpen">
      <ul>
        <li><a href="#about-me" @click="toggleMenu">À propos</a></li>
        <li><a href="#skills" @click="toggleMenu">Compétences</a></li>
        <li><a href="#projects" @click="toggleMenu">Projets</a></li>
        <li><a href="#contact" @click="toggleMenu">Contact</a></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
.header {
  background: linear-gradient(135deg, #0a0a23, #1c1c46);
  color: #fff;
  padding: 20px;
  font-family: "Poppins", sans-serif;
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.4);
}

.header-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1100px;
  margin: auto;
}

.logo {
  font-size: 1.6rem;
  color: #00d1ff;
  letter-spacing: 1px;
}

/* --- Navigation Desktop --- */
.nav-desktop ul {
  display: flex;
  list-style: none;
  gap: 30px;
  margin: 0;
  padding: 0;
}

.nav-desktop a {
  color: #dcdcdc;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s;
}

.nav-desktop a:hover {
  color: #00d1ff;
}

/* --- Burger --- */
.burger {
  display: none;
  flex-direction: column;
  justify-content: center;
  width: 30px;
  height: 25px;
  background: none;
  border: none;
  cursor: pointer;
  position: relative;
}

.burger span,
.burger span::before,
.burger span::after {
  content: "";
  display: block;
  height: 3px;
  width: 100%;
  background: #fff;
  border-radius: 3px;
  position: absolute;
  transition: all 0.3s ease;
}

.burger span::before {
  transform: translateY(-8px);
}

.burger span::after {
  transform: translateY(8px);
}

.burger span.open {
  background: transparent;
}

.burger span.open::before {
  transform: rotate(45deg);
}

.burger span.open::after {
  transform: rotate(-45deg);
}

/* --- Menu Mobile --- */
.nav-mobile {
  background: rgba(10, 10, 35, 0.95);
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  padding: 20px 0;
  text-align: center;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.nav-mobile ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-mobile li {
  margin: 15px 0;
}

.nav-mobile a {
  color: #dcdcdc;
  text-decoration: none;
  font-size: 1.1rem;
  transition: color 0.3s;
}

.nav-mobile a:hover {
  color: #00d1ff;
}

/* --- Responsive --- */
@media (max-width: 768px) {
  .nav-desktop {
    display: none;
  }

  .burger {
    display: flex;
  }
}
</style>
