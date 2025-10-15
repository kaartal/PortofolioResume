<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css');

.infoBar {
  position: fixed;
  top: 20px;
  right: 20px;
  display: flex;
  gap: 4px;
  z-index: 2;
  animation: slideInRight 2.8s ease-out forwards, floatY 1s ease-in-out infinite 2.8s;
  user-select: none;
  opacity: 0;
}


@keyframes slideInRight {
  0% {
    transform: translateX(80px);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}




.infoItem {
  background-color: #0e0e0e;
  color: #fff;
  border-radius: 8px;
  padding: 4px 8px;
  font-size: 12px;
  display: flex;
  align-items: center;
  gap: 4px;
  border: 1px solid #222;
  box-shadow: 0 0 5px rgba(255, 255, 255, 0.05);
  user-select: none;
}

.infoItem i {
  color: #720e9e;
  font-size: 12px;
}

@media (max-width: 1024px) {
  .infoBar {
    display: none;
  }
}
</style>

<template>
  <div class="infoBar">
    <div class="infoItem">
      <i class="fas fa-map-marker-alt"></i>
      <span>Tuzla</span>
    </div>
    <div class="infoItem">
      <i class="fas fa-globe"></i>
      <span>UTC+2</span>
    </div>
    <div class="infoItem">
      <i class="fas fa-clock"></i>
      <span>{{ formattedTime }}</span>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, computed } from 'vue'

const time = ref(new Date())

function updateTime() {
  time.value = new Date()
}

let interval

onMounted(() => {
  updateTime()
  interval = setInterval(updateTime, 1000)
})

onUnmounted(() => {
  clearInterval(interval)
})

const formattedTime = computed(() =>
  time.value.toLocaleTimeString('bs-BA', {
    timeZone: 'Europe/Sarajevo',
    hour: '2-digit',
    minute: '2-digit',
  })
)
</script>
