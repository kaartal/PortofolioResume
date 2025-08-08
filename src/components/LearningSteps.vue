<template>
  <div class="timeline-container">
    <div v-for="entry in timeline" :key="entry.year" class="timeline-entry">
      <div class="timeline-year">
        <div class="circle"></div>
  
      </div>
      <ul class="timeline-items">
        <li v-for="(item, index) in entry.items" :key="index">
          <span class="check-icon">✔</span> {{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
const timeline = [
  {
    year: '2024',
    items: [
      'Graduated from college with a degree in Computer Science',
      'Started working at Sophos as a Threat Researcher',
      'Started my journey to interact with the community (majorly X)',
    ],
  },
  {
    year: '2023',
    items: [
      'Getting more clients for my freelance work',
      'Started learning Python Now',
      'Started working on my personal projects',
    ],
  },
  {
    year: '2022',
    items: [
      'Started learning React and Firebase',
      'Started working on my personal projects',
      'Started my journey in the freelancing world',
    ],
  },
];
</script>

<style scoped>
.timeline-container {
  max-width: 700px;
  margin: auto;
  padding: 2rem 1rem;
  position: relative;
  border-left: 3px solid #A04DFF; 
}


.timeline-entry {
  margin-bottom: 3rem;
  position: relative;
  padding-left: 2rem;
}

.timeline-year {
    
  display: flex;
  align-items: center;
  margin-bottom: 2rem;
}

.timeline-year h3 {
  font-size: 1.2rem;
  font-weight: 700;
  color: #fff;
}

.circle {
  position: absolute;
  left: -24px; 
  top: 3px; 
  width: 14px;
  height: 14px;
  background-color: #A04DFF; 
  border-radius: 50%;
  z-index: 2;
}

.timeline-items li {
  list-style: none;
  margin-bottom: 0.7rem;
  color: #ccc;
  font-size: 0.95rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}
.timeline-entry {
  margin-bottom: 3rem;
  position: relative;
  padding-left: 2.5rem; 
}
.check-icon {
  color: #A04DFF; 
  font-weight: bold;
}

.timeline-entry:not(:last-child)::after {
  content: "";
  position: absolute;
  left: -3px;
  top: 45px;
  height: calc(100% - 45px);
  border-left: 1px dashed #444;
  display:none;
}

@media (max-width: 768px) {
  .timeline-container {
    margin-left:20px;
  }
  
  .circle {
  width: 12px;
  height: 12px;
}


.timeline-entry {
  margin-bottom: 3rem;
  position: relative;
  padding-left: 0.4rem;
}
  }
</style>
