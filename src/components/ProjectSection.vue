<template>
  <div class="projectsBox">
    <h2 class="sectionName">My Projects</h2>
    <p class="description">
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
          faded: index !== activeProjectIndex,
          bounce: index === activeProjectIndex
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

const activeProjectIndex = ref(1);
const projectRefs = ref([]);
const setActive = async (index) => {
  activeProjectIndex.value = index;

  await nextTick(); 

  const el = projectRefs.value[index];
  if (el && el.scrollIntoView) {
    el.scrollIntoView({ behavior: 'smooth', block: 'center' });
  }
};

const projects = [
  {
    title: "Array Sorting Visualizer",
    date: "2022",
    description: "Created a visualizer using JavaScript to show how sorting algorithms work visually.",
    tags: ["HTML", "CSS", "JavaScript"],
    source: "#",
    image: new URL('@/assets/begitam.png', import.meta.url).href,
  },
  {
    title: "Kurma",
    date: "Oct 2024 – Present",
    description: "Created a visualizer using JavaScript to show how sorting algorithms work visually.",
    tags: ["Python", "Streamlit", "AI", "UI"],
    source: "#",
    image: new URL('@/assets/begitam.png', import.meta.url).href,
  },
  {
    title: "My Third Project",
    date: "2025",
    description: "Created a visualizer using JavaScript to show how sorting algorithms work visually.",
    tags: ["Vue", "Tailwind"],
    source: "#",
    image: new URL('@/assets/begitam.png', import.meta.url).href,
  },
];



</script>

<style scoped>
.projectsBox {
  max-width: 1200px;
  margin: auto;
  padding: 2rem 1rem;
  text-align: center;
  margin-bottom: 300px;
}

.sectionName {
  font-size: 2.2rem;
  margin-bottom: 20px;
  font-weight: 700;
  color: #fff;
}

.description {
  font-size: 1rem;
  color: #ccc;
  margin-bottom: 70px;
}

.projectGrid {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 2rem;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  padding: 2rem 0;
}

.projectItem {
  background: linear-gradient(135deg, #ff4d5a, #b85fff);
  border-radius: 12px;
  overflow: hidden;
  width: 350px;
  display: flex;
  flex-direction: column;
  transition: transform 0.4s ease, opacity 0.4s ease;
  cursor: pointer;
  scroll-snap-align: center;
  height: 500px;
  position: relative;
}

.projectItem:hover {
  transform: translateY(-5px);
}

.projectItem.active {
  transform: scale(1);
  opacity: 1;
  z-index: 2;
}

.projectItem.faded {
  transform: scale(0.9);
  opacity: 0.4;
  filter: brightness(0.3);
}

/* Bounce animation */
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-8px);
  }
}

.bounce {
  animation: bounce 1.4s infinite;
}

.projectLogo img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  display: block;
}

.projectContent {
  background-color: #111;
  padding: 1rem;
  text-align: left;
  color: #fff;
  height: 400px;
}

.sourceButton {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background-color: #00aaff;
  color: #fff;
  text-decoration: none;
  padding: 0.5rem 1rem;
  border-radius: 6px;
  font-size: 0.9rem;
  font-weight: 600;
  transition: background-color 0.3s ease, transform 0.2s ease;
  box-shadow: 0 2px 8px rgba(0, 170, 255, 0.4);
}

.sourceButton:hover {
  background-color: #008ecc;
  transform: translateY(-2px);
}

.sourceLogo {
  width: 18px;
  height: 18px;
  object-fit: contain;
}

.projectName {
  font-size: 1.2rem;
  font-weight: 600;
  margin: 1;
  margin-top: 10px;
}

.projectDescription {
  font-size: 0.95rem;
  margin-bottom: 2rem;
  color: #ccc;
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
  padding: 0.3rem 0.6rem;
  border-radius: 5px;
  font-size: 0.8rem;
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
  box-shadow: 0 2px 6px rgba(0, 170, 255, 0.3);
}

.links a:hover {
  background-color: #008ecc;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .projectGrid {
    flex-direction: column;
    align-items: center;
  }

  .projectItem {
    width: 100%;
  }
}
</style>
