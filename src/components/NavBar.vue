<template>
  <nav :class="['navbarBox', { navbarHidden: isHidden }]">
    <div class="logoPic"> 
      <img :src="logo" alt="HK Logo" class="logoImage" />
    </div>
    <button class="hamburger" @click="toggleMenu" aria-label="Toggle menu">
      <span :class="{ bar1: true, open: menuOpen }"></span>
      <span :class="{ bar2: true, open: menuOpen }"></span>
      <span :class="{ bar3: true, open: menuOpen }"></span>
    </button>

    <ul :class="['navigationLinks', { open: menuOpen }]">
      <li v-for="link in links" :key="link.id">
        <a
          :href="`#${link.id}`"
          :class="{ active: activeSection === link.id }"
          @click.prevent="scrollToSection(link.id); closeMenu()"
        >
          {{ link.name }}
        </a>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';
import logo from '@/assets/download.svg';

const links = [
  { id: 'about', name: 'About' },
  { id: 'projects', name: 'Skills' },
  { id: 'testimonials', name: 'Projects' },
  { id: 'contact', name: 'Timeline' },
];

const activeSection = ref(null);
const isHidden = ref(false);
const menuOpen = ref(false);

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value;
};

const closeMenu = () => {
  menuOpen.value = false;
};

function scrollToSection(id) {
  const el = document.getElementById(id);
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' });
  }
}

function onScroll() {
  let current = null;
  links.forEach(link => {
    const section = document.getElementById(link.id);
    if (section) {
      const rect = section.getBoundingClientRect();
      if (rect.top <= 80) {
        current = link.id;
      }
    }
  });
  activeSection.value = current;

  const scrollTop = window.scrollY || window.pageYOffset;
  const docHeight = document.documentElement.scrollHeight - window.innerHeight;
  const scrolledPercent = scrollTop / docHeight;

  isHidden.value = scrolledPercent > 0.3;

  if (isHidden.value) {
    closeMenu();
  }
}

onMounted(() => {
  window.addEventListener('scroll', onScroll);
  onScroll();
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', onScroll);
});
</script>

<style scoped>
.navbarBox {
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  padding: 16px 24px;
  background: rgba(17, 23, 40, 0.85);
  border-radius: 12px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.45);
  backdrop-filter: blur(1px);
  width: fit-content;
  z-index:2;
  user-select: none;
  transition: opacity 0.8s ease, transform 0.8s ease;
}

.navbarHidden {
  opacity: 0;
  pointer-events: none;
  transform: translateY(-20px);
}

.logoPic {
  position: absolute;
  left: -90px;
}

.logoImage {
  height: 50px;
  user-select: none;
  margin-top:10px;
}

.hamburger {
  display: none;
  flex-direction: column;
  justify-content: space-around;
  width: 26px;
  height: 22px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  box-sizing: border-box;
  z-index: 10000;
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

.bar3.open {
  transform: rotate(-45deg);
}

/* Navigacioni linkovi */
.navigationLinks {
  list-style: none;
  display: flex;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

.navigationLinks li a {
  color: #fff;
  font-weight: 500;
  text-decoration: none;
  padding: 10px 16px;
  border-radius: 8px;
  transition: background-color 0.3s ease;
  cursor: pointer;
  font-size: 1rem;
  user-select: none;
}

.navigationLinks li a:hover,
.navigationLinks li a.active {
  background-color: #3b3f5c;
  color: #fff;
}

/* Mobilni prikaz */
@media (max-width: 768px) {
  .navbarBox {
    gap: 1.5rem;
    padding: 10px 16px;
    justify-content: center;
    position: fixed;
    top: 20px;
    left: 50%;
    transform: translateX(-50%);
    width: 100%;
    max-width: 480px;
    border-radius: 12px;

    background-color: transparent !important;
    background-image: none !important;
  }
  
  .logoPic {
    position: static;
    margin: 0 auto;
    order: 1;
    left: auto;
  }

  /* Pomeramo hamburger u desni ugao */
  .hamburger {
    display: flex;
    position: absolute;
    top: 50%;
    right: 20px;
    transform: translateY(-50%);
  }

  /* Sakrij linkove po defaultu */
  .navigationLinks {
    position: fixed;
    top: 0;
    right: 0;
    height: 20vh;
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
    z-index: 9999;
  }

  .navigationLinks.open {
    opacity: 1;
    pointer-events: auto;
    transform: translateX(0);
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
    display:none;
  }
}
</style>
