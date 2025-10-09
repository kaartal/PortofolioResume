<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@700&display=swap');

.timelineTitle {
  text-align: center;
  font-size: 3rem;
  font-weight: 700;
  color: #a04dff;
  font-family: 'Orbitron', sans-serif;
  user-select: none;
  opacity: 0;
  transition: opacity 1.2s ease;
  margin-bottom: 4rem;
  visibility: hidden;
  padding-top: 100px;
  transform: translateZ(0);
  will-change: transform;
}

.timelineTitle.visible {
  opacity: 1;
  visibility: visible;
  animation: floatUpDown 3s ease-in-out infinite;
  transform: translateY(0); 
}

.underTitleLine {
    width: 280px;
    height: 8px;
    background-color: #a04dff;
    margin: 0 auto;
    margin-top: -48px;
    border-radius: 22px;

    clip-path: polygon(
        0% 60%, 
        10% 50%, 
        20% 55%, 
        30% 45%, 
        40% 50%, 
        50% 40%, 
        60% 55%, 
        70% 50%, 
        80% 60%, 
        90% 45%, 
        100% 50%,
        100% 100%, 
        0% 100%
    );
}

@keyframes floatUpDown {
  0%,
  100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-5px);
  }
}

.timelineContainer {
  max-width: 800px;
  margin: auto;
  padding: 2rem 1rem;
  position: relative;
  border-left: px solid #a04dff;
  margin-bottom: 120px;
}

.timelineYearGroup {
  margin-bottom: 2.5rem;
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.6s ease;
  position: relative;
  transform: translateZ(0);
  will-change: transform;
}

.timelineYearGroup.visible {
  opacity: 1;
  transform: translateY(0);
}

.yearRow {
  display: flex;
  align-items: center;
  margin-bottom: 0.5rem;
}

.circle {
  position: absolute;
  left: -25px;
  width: 14px;
  height: 14px;
  background-color: #a04dff;
  border-radius: 50%;
  animation: pulseGlow 2s infinite ease-in-out;
}

.yearLabel {
  color: #a04dff;
  font-weight: bold;
  font-size: 1.9rem;
  margin-left: 1.2rem;
  margin-bottom: 0.3rem;
  margin-top: 4px;
  font-family: 'Orbitron', 'Poppins';
font-size: 22px; 
letter-spacing: 2px; 
line-height: 1.5; 
transform: translateZ(0);
  will-change: transform;
}

.yearItems {
  list-style: none;
  margin: 0;
  padding: 0 0 0 1.5rem;
}

.yearItem {
  color: #ccc;
  font-size: 1.05rem;
  margin-bottom: 0.3rem;
  margin-left: 10px;
  font-family: 'Orbitron', 'Poppins';
font-size: 17px; 
letter-spacing: 2px; 
line-height: 1.5; 
transform: translateZ(0);
  will-change: transform;
}

/* RESPONSIVE DESIGN */
@media (max-width: 1024px) {
  .timelineContainer {
      margin-left: 170px;
    border-left-width: 4px;
  }
}

/* MOBILE DESIGN */
@media (max-width: 768px) {
  .timelineContainer {
    margin-left: 40px;
    border-left-width: 4px;  
  }

  .circle {
    width: 12px;
    height: 12px;
  }

  .yearLabel {
    font-size: 1rem;
  }

  .yearItem {
    font-size: 0.95rem;
  }
}

@keyframes pulseGlow {
  0% {
    box-shadow: 0 0 3px #a04dff, 0 0 10px #a04dff;
    transform: scale(1);
  }
  50% {
    box-shadow: 0 0 10px #a04dff, 0 0 25px #a04dff;
    transform: scale(1.1);
  }
  100% {
    box-shadow: 0 0 3px #a04dff, 0 0 10px #a04dff;
    transform: scale(1);
  } 
}

.timelineYearGroup.visible {
  animation: floatUpDown 3s ease-in-out infinite;
}
</style>

<template>
  
    <div id="timeline"></div>

    <!-- TIMELINE TITLE -->
  <div ref="titleRef" :class="['timelineTitle', { visible: titleVisible }]">
    my steps
  </div>
  <div class="underTitleLine"></div>

  <div class="timelineContainer">
    <div
      v-for="(entry, i) in timeline"
      :key="i"
      class="timelineYearGroup"
      ref="timelineItems"
    >
      <div class="yearRow">
        <div class="circle"></div>
        <div class="yearLabel">{{ entry.year }}</div>
      </div>

      <ul class="yearItems">
        <li v-for="(item, j) in entry.items" :key="j" class="yearItem">
          {{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, nextTick } from "vue";

const titleRef = ref(null);
const titleVisible = ref(false);
const timelineItems = ref([]);

const timeline = ref([
  {
    year: "2025",
    items: [
      "I earned a Bachelor's degree in Information Technology",
      "Began development using Vue.js framework",
      "Created this Developer Portofolio",
    ],
  },
  {
    year: "2024",
    items: [
      "Started learning backend development with .NET Core and C#",
      "Completed a 3-month remote internship with a USA-based company",
    ],
  },
  {
    year: "2023",
    items: [
      "Adopted Object-Oriented Programming principles in projects",
      "Gained proficiency in database management and design",
      "Developed applications utilizing Shell scripting and C++",
    ],
  },
  {
    year: "2022",
    items: ["Enrolled in a Bachelor’s program in Information Technology"],
  },
  {
    year: "2021",
    items: [
      "Initiated work on personal projects to build practical experience",
      "Started programming with C++ on Linux environments",
    ],
  },
]);

onMounted(async () => {
  await nextTick();

  if (titleRef.value) {
    const titleObserver = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          titleVisible.value = entry.isIntersecting;
        });
      },
      { threshold: 0.5 }
    );
    titleObserver.observe(titleRef.value);
  }

  const items = timelineItems.value;
  if (items.length > 0) {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            entry.target.classList.add("visible");
          } else {
            entry.target.classList.remove("visible");
          }
        });
      },
      { threshold: 0.1 }
    );

    items.forEach((el) => observer.observe(el));
  }
});
</script>


