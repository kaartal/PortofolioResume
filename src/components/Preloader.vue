<template>
  <div class="preloader">
    <div class="codeBox">
      <div class="windowsButtons">
        <span class="windowButton red"></span>
        <span class="windowButton yellow"></span>
        <span class="windowButton green"></span>
      </div>
      <pre>{{ displayedCode }}<span class="cursor"></span></pre>
    </div>
  </div>
</template>


<script setup>
import { ref, onMounted } from 'vue'

const fullCode = `
console.log("☕ Making coffee");
console.log("💻 Compiling focus");
console.log("✅ Developer mode: ON");
`;

const displayedCode = ref('');
let index = 0;

onMounted(() => {
  const typingSpeed = 25; 

  const type = () => {
    if (index < fullCode.length) {
      displayedCode.value += fullCode[index];
      index++;
      setTimeout(type, typingSpeed);
    }
  };

  type();
});

const emit = defineEmits(['done']); 

onMounted(() => {
  const typingSpeed = 25;

  const type = () => {
    if (index < fullCode.length) {
      displayedCode.value += fullCode[index];
      index++;
      setTimeout(type, typingSpeed);
    } else {
      
      emit('done');
    }
  };

  type();
});

</script>

<style scoped>
.preloader {
  position: fixed;
  inset: 0;
  background-color: rgba(13, 13, 26, 0.85); 
  backdrop-filter: blur(6px); 
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  font-family: 'Courier New', monospace;
  color: #A04DFF;
  user-select: none;
  overflow: hidden;
}


.codeBox {
  background: #0f111a;
  padding: 2rem 2.5rem;
  border-radius: 12px;
  box-shadow:
    0 0 15px #A04DFF(0, 255, 174, 0.6),
    inset 0 0 5px #A04DFF(0, 255, 174, 0.3);
  max-width: 90%;
  max-height: 80%;
  overflow-y: auto;
  white-space: pre-wrap;
  border: 1.5px solid #A04DFF;
  position: relative;
  min-width: 320px;
}


.windowsButtons {
  position: absolute;
  top: 12px;
  left: 16px;
  display: flex;
  gap: 8px;
}

.windowButton {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  box-shadow: 0 0 4px rgba(0,0,0,0.3);
}

.windowButton.red {
  background: #ff5f56;
}

.windowButton.yellow {
  background: #ffbd2e;
}

.windowButton.green {
  background: rgb(0, 202, 86); 
}


.cursor {
  display: inline-block;
  width: 8px;
  height: 18px;
  background-color: #A04DFF;
  margin-left: 2px;
  animation: blink 1.2s steps(2, start) infinite;
  vertical-align: bottom;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}
</style>

