<template>
  <canvas ref="canvas"></canvas>
  <div
    ref="cursor"
    class="customCurosr"
    :style="{ left: mouse.x + 'px', top: mouse.y + 'px' }"
  >
    <div class="outsideCircle"></div>
    <div class="innerCircle"></div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const canvas = ref(null);
const cursor = ref(null);
const mouse = ref({ x: -100, y: -100 });

let ctx, stars = [], animationId;
const numStars = 500;

class Star {
  constructor() {
    this.reset();
  }

  reset() {
    this.x = Math.random() * window.innerWidth;
    this.y = Math.random() * window.innerHeight;
    this.size = Math.random() * 1.5;
    this.speed = Math.random() * 0.2 + 0.05;
    this.alpha = Math.random() * 0.5 + 0.3;
  }

  update() {
    this.y += this.speed;
    if (this.y > window.innerHeight) {
      this.reset();
      this.y = 0;
    }
  }

  draw() {
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(255, 255, 255, ${this.alpha})`;
    ctx.fill();
  }
}

function createStars() {
  stars = [];
  for (let i = 0; i < numStars; i++) {
    stars.push(new Star());
  }
}

function animate() {
  ctx.fillStyle = '#0d0d1a';
  ctx.fillRect(0, 0, canvas.value.width, canvas.value.height);

  stars.forEach(star => {
    star.update();
    star.draw();
  });

  animationId = requestAnimationFrame(animate);
}

function resizeCanvas() {
  canvas.value.width = window.innerWidth;
  canvas.value.height = window.innerHeight;
  createStars();
}

function handleMouseMove(e) {
  mouse.value.x = e.clientX;
  mouse.value.y = e.clientY;
}

onMounted(() => {
  ctx = canvas.value.getContext('2d');
  resizeCanvas();
  window.addEventListener('resize', resizeCanvas);
  window.addEventListener('mousemove', handleMouseMove);
  animate();
});

onUnmounted(() => {
  cancelAnimationFrame(animationId);
  window.removeEventListener('resize', resizeCanvas);
  window.removeEventListener('mousemove', handleMouseMove);
});
</script>

<style scoped>
canvas {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: -1;
  pointer-events: none;
}

.customCurosr {
  position: fixed;
  pointer-events: none;
  transform: translate(-50%, -50%);
  z-index: 999999; 
  top: 0;
  left: 0;
  user-select: none;
  mix-blend-mode: difference; 
}

.outsideCircle {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: white;
}

.innerCircle {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 12px;
  height: 12px;
  background: black;
  border-radius: 50%;
  transform: translate(-50%, -50%);
}
</style>
