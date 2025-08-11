<template>
  <nav :class="['navbarBox', { navbarHidden: isHidden }]">
    <!-- Logo i navigacija će biti vidljivi samo na desktopu -->
    <div class="logoPic"> 
      <img :src="logo" alt="HK Logo" class="logoImage" />
    </div>

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

    <!-- Hamburger dugme uvek prikazano, ali samo na mobilnom -->
    <button class="hamburger" @click="toggleMenu" aria-label="Toggle menu">
      <span :class="{ bar1: true, open: menuOpen }"></span>
      <span :class="{ bar2: true, open: menuOpen }"></span>
      <span :class="{ bar3: true, open: menuOpen }"></span>
    </button>
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

let lastScrollTop = 0;

function onScroll() {
  const scrollTop = window.scrollY || window.pageYOffset;

  // Sakrij navbar ako skroluješ (bilo gde osim na vrhu)
  if (scrollTop > 0) {
    isHidden.value = true;
    closeMenu();
  } else {
    // Ako si na vrhu stranice, prikaži navbar
    isHidden.value = false;
  }

  // Aktivna sekcija - opcionalno, možeš i ukloniti ako ti ne treba
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
  gap: 3rem;
  padding: 16px 24px;
  background: rgba(17, 23, 40, 0.85);
  border-radius: 12px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.45);
  backdrop-filter: blur(1px);
  width: fit-content;
  z-index: 2;
  user-select: none;
  transition: opacity 0.4s ease, transform 0.4s ease;
}

.navbarHidden {
  opacity: 0;
  pointer-events: none;
  transform: translate(-50%, -100%);
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
  .navigationLinks {
    position: fixed;
    top: 0;
    right: 0;
    height: 100vh;
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

  .hamburger {
    display: flex;
    position: absolute;
    top: 24px;
    right: 24px;
    flex-direction: column;
    justify-content: space-around;
    width: 26px;
    height: 22px;
    background: transparent;
    border: none;
    cursor: pointer;
    z-index: 10000;
  }

  .navbarBox {
    width: 100%;
    justify-content: space-between;
    padding: 16px;
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
    display:none;
  }
}
</style>
