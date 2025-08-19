<template>
  <div class="clock">
    <div class="location">Tuzla, Bosna i Hercegovina</div>
    <div class="time">{{ formattedTime }}</div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, computed } from 'vue';

const time = ref(new Date());

function updateTime() {
  time.value = new Date();
}

let interval;

onMounted(() => {
  updateTime();
  interval = setInterval(updateTime, 1000);
});

onUnmounted(() => {
  clearInterval(interval);
});

const formattedTime = computed(() =>
  time.value.toLocaleTimeString('bs-BA', {
    timeZone: 'Europe/Sarajevo',
    hour: '2-digit',
    minute: '2-digit',
    second: '2-digit',
  })
);
</script>

<style scoped>
.clock {
  position: fixed;
  bottom: 10px;
  right: 10px;
  font-family: 'Orbitron', sans-serif;
  font-weight: 600;
  font-size: 10px;
  color: white;
  text-align: right;
  user-select: none;
  z-index: 1;
}

.location {
  font-size: 8px;
  opacity: 0.8;
  letter-spacing: 1px;
}

.time {
  font-size: 8px;
  font-weight: bold;
  letter-spacing: 1.5px;
}

@media (max-width: 768px) {
  .clock{
    display:none;
  }
  }
</style>
