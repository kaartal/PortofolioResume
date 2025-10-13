<style scoped>
.projectsBox {
  max-width: 1200px;
  margin: auto;
  padding: 2rem 1rem;
  text-align: center;
  margin-bottom: 300px;
  margin-top: 300px;
  padding-top: 80px;
}

.sectionName{
    opacity: 0;
  transform: translateY(20px);
  color: white;
  font-family: 'Orbitron', sans-serif;
  animation-fill-mode: forwards;
  transition: opacity 1.8s ease, transform 1.8s ease;
  margin-bottom:20px;
  font-size:3.5rem;
  user-select: none;
  transform: translateZ(0);
  will-change: transform;
}

.description {
  opacity: 0;
  transform: translateY(20px);
  color: white;
  font-family: "Copperplate", "Copperplate Gothic Light";
  animation-fill-mode: forwards;
  transition: opacity 0.8s ease, transform 0.8s ease;
  margin-bottom:42px;
  font-size:18px;
  user-select: none;
  transform: translateZ(0);
  will-change: transform;
}

.animate.sectionName,
.animate.description {
  opacity: 1;
  transform: translateY(0);
  animation: floatSmooth 6s ease-in-out infinite;
}

@keyframes floatSmooth {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-5px);
  }
}

.projectGrid {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 2rem;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  padding: 1rem 0;
}

.projectItem {
  background: linear-gradient(135deg, #ff4d5a, #b85fff);
  border-radius: 12px;
  overflow: hidden;
  width: 350px;
  display: flex;
  flex-direction: column;
  cursor: pointer;
  scroll-snap-align: center;
  height: 620px;
  position: relative;
  opacity: 0.5;
  transform: translateY(10px);
  transition:
    opacity 0.6s ease,
    transform 0.6s ease;
  animation: floatSmooth 6s ease-in-out infinite;
  font-family: 'Poppins', sans-serif;
  box-shadow: 0 2px 1px rgba(176, 83, 255, 0.7);
}

.projectItem.active {
  opacity: 1;
  transform: translateY(0);
  z-index: 2;
  box-shadow: 0 1px px rgba(176, 83, 255, 0.7);
  animation: floatSmooth 4s ease-in-out infinite;
}

.projectItem.faded {
  opacity: 0.4;
  transform: scale(0.9);
  filter: brightness(0.6);
  animation: none;
}

.projectItem:hover {
  animation-play-state: paused;
}

.projectLogo img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  display: block;
}

.projectContent {
  background-color: #111;
  padding: 1rem;
  text-align: left;
  color: #fff;
  height: 420px;
}

.sourceButton {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background-image: linear-gradient(to right top, #6c239b, #62228e, #582182, #4e2075, #451e69);
  color: #fff;
  text-decoration: none;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  font-size: 0.9rem;
  font-weight: 600;
  transition: background-color 0.3s ease, transform 0.2s ease;
  font-family: 'Orbitron', sans-serif;
}

.sourceButton:hover {
  transform: translateY(-2px);
}

.sourceLogo {
  width: 18px;
  height: 18px;
  object-fit: contain;
}

.projectName {
  font-size: 1.4rem;
  font-weight: 600;
  margin-top: 10px;
}

.projectDescription {
  font-size: 1.0rem;
  margin-bottom: 2rem;
  color: #ccc;
}

.projectDateOfProduct{
  margin-top:-15px;
  margin-bottom:-10px;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.tag {
  background-color: #222;
  color: #ccc;
  padding: 0.4rem 0.7rem;
  border-radius: 5px;
  font-size: 0.7rem;
  box-shadow: 0 1px 1px rgba(176, 83, 255, 0.7);
  font-family: 'Orbitron', sans-serif;
}

.links {
  display: flex; 
  gap: 1rem;
}

.links a {
  background-color: #00aaff;
  color: #fff;
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 500;
  transition: background-color 0.3s ease, transform 0.2s ease;
}

.links a:hover {
  background-color: #008ecc;
  transform: translateY(-1px);
}

@media (max-width: 768px) {
  .projectGrid {
    flex-direction: column;
    align-items: center;
    margin-bottom:-240px;
  }

  .projectBox{
    margin-bottom:-240px;
  }

  .projectItem {
    width: 100%;
    height:570px;
  }
}
</style>


<template>
  <div class="projectsBox">
    <h2 class="sectionName" :class="{ animate: isVisible }" ref="titleRef">selected projects</h2>
    <p class="description" :class="{ animate: isVisible }" ref="descriptionRef">
      I’m passionate about turning ideas into real, useful products and I love sharing what I learn along the way.
    </p>

    <div class="projectGrid">
      <div
        v-for="(project, index) in projects"
        :key="project.title"
        :ref="el => projectRefs[index] = el"
        class="projectItem"
        :class="{
          active: index === activeProjectIndex,
          faded: index !== activeProjectIndex
        }"
        @click="setActive(index)"
      >
        <div class="projectLogo">
          <img :src="project.image" :alt="project.title" />
        </div>
        <div class="projectContent">
          <h3 class="projectName">{{ project.title }}</h3>
          <p class="projectDateOfProduct">{{ project.date }}</p>
          <p class="projectDescription">{{ project.description }}</p>
          <div class="tags">
            <span class="tag" v-for="tag in project.tags" :key="tag">{{ tag }}</span>
          </div>
          <div class="links">
            <a :href="project.source" target="_blank" class="sourceButton">
              <img src="@/assets/github.png" alt="GitHub Logo" class="sourceLogo" />
              Source
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, nextTick } from 'vue';

const isVisible = ref(false);
const titleRef = ref(null);
const descriptionRef = ref(null);

const activeProjectIndex = ref(1);
const projectRefs = ref([]);

const setActive = async (index) => {
  activeProjectIndex.value = index;

  await nextTick();

  const el = projectRefs.value[index];

};

const projects = [
  {
    title: "vehicleregistration.html",
    date: "Mar 2024 - Apr 2024",
    description: "I developed a full-stack web application that simulates real-world vehicle registration processes. The application allows users to register vehicles, manage ownership records, issue license plates, and track registration history.",
    tags: ["PHP", "CSS", "HTML", "MySQL"],
    source: "https://github.com/kaartal/VehicleRegistration",
    image: new URL('@/assets/carregistration.png', import.meta.url).href,
  },
  {
    title: "ticketshop.cs",
    date: "Dec 2025 – Jun 2025",
    description: "Developed a comprehensive online ticketing platform that facilitates the seamless sale and real-time tracking of digital tickets.",
    tags: [".NET", "C#", "EF", "HTML", "CSS", "JavaScript", "SQL"],
    source: "https://github.com/kaartal/FootballTickets",
    image: new URL('@/assets/ticket.avif', import.meta.url).href,
  },
  {
    title: "bank.cpp",
    date: "Mar 2024 - May 2024",
    description: "I designed and implemented a desktop-based banking simulation system in C++, focusing on replicating real-world banking processes and account management.",
    tags: ["C++", "C"],
    source: "https://github.com/kaartal/BankSystem",
    image: new URL('@/assets/bank.jpg', import.meta.url).href,
  },
];

onMounted(async () => {
  await nextTick();

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.target === titleRef.value || entry.target === descriptionRef.value) {
          isVisible.value = entry.isIntersecting;
        }
      });
    },
    { threshold: 0.2 }
  );

  if (titleRef.value) observer.observe(titleRef.value);
  if (descriptionRef.value) observer.observe(descriptionRef.value);
});
</script>

