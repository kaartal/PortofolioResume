<style scoped>
.navbarBox {
  position: fixed;
  top: 30px;
  left: 50%;
  transform: translate(-50%, 0);
  display: flex;
  align-items: center;
  gap: 3rem;
  padding: 16px 24px;
  background: rgba(17, 23, 40, 0.85);
  border-radius: 24px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.45);
  backdrop-filter: blur(4px);
  width: fit-content;
  z-index: 4;
  user-select: none;
  animation: floatNav 8s ease-in-out infinite;
}

@keyframes floatNav {
  0%, 100% {
    transform: translate(-50%, 0);
  }
  50% {
    transform: translate(-50%, 7px);
  }
}

.navbarHidden {
  opacity: 0;
  pointer-events: none;
  transform: translate(-50%, -100%);
}

.logoPic {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 120px;
  height: 120px;
  background-color: #1e1e1e;
  border-radius: 20px;
}

.logoText {
  font-family: 'Montserrat', sans-serif;
  font-size: 48px;
  font-weight: 700;
  color: #00d8ff; 
  letter-spacing: 5px; 
  text-shadow: 2px 2px 6px rgba(0,0,0,0.3); 
}

.hamburger {
  display: none;
}

.hamburger span {
  width: 26px;
  height: 3px;
  background: #fff;
  border-radius: 2px;
  transition: all 0.3s ease;
  transform-origin: 1px;
}

.bar1.open {
  transform: rotate(45deg);
}

.bar2.open {
  opacity: 0;
}
.navbarBox {
  transition: opacity 0.4s ease, transform 0.4s ease;
}

.navbarHidden {
  opacity: 0;
  transform: translateY(-100%);
}
.bar3.open {
  transform: rotate(-45deg);
}

.navigationLinks {
  list-style: none;
  display: flex;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

.navigationLinks li a {
  font-family: 'Orbitron', sans-serif;
  color: #fff;
  font-weight: 500;
  text-decoration: none;
  padding: 10px 16px;
  border-radius:20px;
  transition: background-color 0.3s ease;
  cursor: pointer;
  font-size: 1.2rem;
  user-select: none;
}

.navigationLinks li a:hover,
.navigationLinks li a.active {
  background-color: #3b3f5c;
  color: #fff;
  border-radius:20px;
}

/* RESPONSIVE MOBILE */
@media (max-width: 768px) {
  .navigationLinks {
    position: fixed;
    top: 0;
    right: 0;
    height: 24vh;
    background: rgba(17, 23, 40, 0.95);
    border-radius: 0 0 0 12px;
    flex-direction: column;
    gap: 2rem;
    padding: 80px 24px 24px 24px;
    box-shadow: -4px 0 24px rgba(0, 0, 0, 0.6);
    width: 250px;
    max-width: 80vw;
    opacity: 0;
    pointer-events: none;
    transform: translateX(100%);
    transition: opacity 0.3s ease, transform 0.3s ease;
    z-index: 2;
  }
.logoPic {
  display:none;
}

.logoImage {
  display:none;
}
  .navigationLinks.open {
    opacity: 1;
    pointer-events: auto;
    transform: translateX(0);
  }
.hamburger span {
  display: block;
  margin: 4px 0;
}
  .hamburger {
    display: flex;
    position: absolute;
    top: 24px;
    right: 51px;
    flex-direction: column;
    justify-content: space-around;
    width: 32px;
    height: 22px;
    background: transparent;
    border: none;
    cursor: pointer;
    z-index: 2;
  }

  .navbarBox {
    width: 100%;
    justify-content: space-between;
    padding: 16px;
      background: none;
    backdrop-filter: none;
    box-shadow: none;
  }

  .logoPic {
    position: static;
    left: auto;
  }

  .navigationLinks li a {
    font-size: 1.2rem;
    padding: 12px 8px;
    text-align: left;
  }
}

@media (max-width: 480px) {
  .navbarBox {
    max-width: 100%;

  }
}
</style>


<template> 
<head>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  </link>
</head>
  <nav :class="['navbarBox', { navbarHidden: isHidden }]">
    
    <!-- LOGO -->
   <ul :class="['navigationLinks', { open: menuOpen }]">
  <li v-for="link in links" :key="link.id">
    <a
      href="#"
      @click.prevent="scrollToSection(link.id)"
      :class="{ active: activeSection === link.id }"
    >
      {{ link.name }}
    </a>
  </li>
</ul>

<!-- HAMBURGER BUTTON -->
   <button class="hamburger" @click="toggleMenu" aria-label="Toggle menu">
      <span :class="{ bar1: true, open: menuOpen }"></span>
      <span :class="{ bar2: true, open: menuOpen }"></span>
      <span :class="{ bar3: true, open: menuOpen }"></span>
    </button>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

const links = [
  { id: 'about', name: 'About' },
  { id: 'skills', name: 'Skills' },
  { id: 'projects', name: 'Projects' },
  { id: 'timeline', name: 'Timeline' },
];

const menuOpen = ref(false);
const toggleMenu = () => menuOpen.value = !menuOpen.value;
const closeMenu = () => menuOpen.value = false;

const scrollToSection = (id) => {
  const el = document.getElementById(id);
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' });
    closeMenu(); 
  }
};

</script>
