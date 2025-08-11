<template>
  <div class="timeline-container">
    <div v-for="(entry, i) in timeline" :key="i" class="timeline-year-group" ref="timelineItems">
      <div class="year-row">
        <div class="circle"></div>
        <div class="year-label">{{ entry.year }}</div>
      </div>
      <ul class="year-items">
        <li v-for="(item, j) in entry.items" :key="j" class="year-item">{{ item }}</li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const timeline = ref([
  { 
    year: '2025', 
    items: [
      'Engaged in advanced personal projects to enhance skills', 
      'Began development using Vue.js framework' 
    ] 
  },
  { 
    year: '2024', 
    items: [
      'Gained proficiency in database management and design', 
      'Started learning backend development with .NET Core and C#' 
    ] 
  },
  { 
    year: '2023', 
    items: [
      'Adopted Object-Oriented Programming principles in projects', 
      'Developed applications utilizing Shell scripting and C++' 
    ] 
  },
  { 
    year: '2022', 
    items: [
      'Enrolled in a Bachelor’s program in Information Technology' 
    ] 
  },
  { 
    year: '2021', 
    items: [
      'Initiated work on personal projects to build practical experience', 
      'Started programming with C++ on Linux environments' 
    ] 
  }
]);


const timelineItems = ref([]);

onMounted(() => {
  const items = timelineItems.value;

  const observer = new IntersectionObserver(
    entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        } else {
          entry.target.classList.remove('visible');
        }
      });
    },
  );

  items.forEach(el => observer.observe(el));
});
</script>

<style scoped>
.timeline-container {
  max-width: 700px;
  margin: auto;
  padding: 2rem 1rem;
  position: relative;
  border-left: 3px solid #A04DFF;
  margin-bottom:120px;

}

.timeline-year-group {
  margin-bottom: 2.5rem;
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.6s ease;
  position: relative;
}

.timeline-year-group.visible {
  opacity: 1;
  transform: translateY(0);
}

.year-row {
  display: flex;
  align-items: center;
  margin-bottom: 0.5rem;
}

.circle {
  position: absolute;
  left: -25px;
  width: 16px;
  height: 16px;
  background-color: #A04DFF;
  border-radius: 50%;
}

.year-label {
  color: #A04DFF;
  font-weight: bold;
  font-size: 1.7rem;
  margin-left: 1.2rem;
  margin-bottom: 0.7rem;
}

.year-items {
  list-style: none;
  margin: 0;
  padding: 0 0 0 1.5rem;
}

.year-item {
  color: #ccc;
  font-size: 1.05rem;
  margin-bottom: 0.7rem;
  margin-left:10px;
  
}
@media (max-width: 1024px) {
  .timeline-container {
    margin-left: 170px;
    border-left-width: 4px;
  }}

@media (max-width: 768px) {
  .timeline-container {
    margin-left: 60px;
    border-left-width: 4px;
  }

  .circle {
    width: 12px;
    height: 12px;
  }

  .year-label {
    font-size: 1rem;
  }

  .year-item {
    font-size: 0.85rem;
  }
}
@keyframes pulseGlow {
  0% {
    box-shadow: 0 0 3px #A04DFF, 0 0 10px #A04DFF;
    transform: scale(1);
  }
  50% {
    box-shadow: 0 0 10px #A04DFF, 0 0 25px #A04DFF;
    transform: scale(1.1);
  }
  100% {
    box-shadow: 0 0 3px #A04DFF, 0 0 10px #A04DFF;
    transform: scale(1);
  }
}

.circle {
  position: absolute;
  left: -25px;
  width: 16px;
  height: 16px;
  background-color: #A04DFF;
  border-radius: 50%;
  animation: pulseGlow 2s infinite ease-in-out;
}

@keyframes floatUpDown {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-5px);
  }
}

.timeline-year-group.visible {
  animation: floatUpDown 3s ease-in-out infinite;
}

</style>
