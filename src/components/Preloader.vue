<style scoped>
.preloader {
  position: fixed;
  inset: 0;
  background: radial-gradient(circle at center, #111221, #0a0a14);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
  font-family: "Courier New", monospace;
  color: #a04dff;
  overflow: hidden;
}

.preloader.fade-out {
  opacity: 0;
}

.code {
  white-space: pre-wrap;
  font-family: monospace;
  font-size: 20px;
  line-height: 1.7;
}

.codeBox {
  background: #0f111a;
  padding: 2rem 2.5rem;
  border-radius: 16px;
  box-shadow: 0 0 25px rgba(160, 77, 255, 0.6),
  inset 0 0 0px rgba(160, 77, 255, 0.3);
  max-width: 90%;
  min-width: 420px;
  border: 1.5px solid #a04dff;
  position: relative;
  overflow: hidden;
  height:160px;
  overflow-y: 1px; /* dodaj ovo */
}

@keyframes glow {
  0% {
    box-shadow: 0 0 15px rgba(160, 77, 255, 0.5),
      inset 0 0 5px rgba(160, 77, 255, 0.2);
  }
  100% {
    box-shadow: 0 0 30px rgba(160, 77, 255, 0.8),
      inset 0 0 10px rgba(160, 77, 255, 0.4);
  }
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
  box-shadow: 0 0 4px rgba(0, 0, 0, 0.3);
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
  height: 14px;
  background-color: #a04dff;
  margin-left: 2px;
  animation: blink 1.2s steps(2, start) infinite;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}


@keyframes scaleUp {
  from { transform: scale(0.1); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}

@media (max-width: 768px) {
  .codeBox {
    min-width: auto;
    width: 90%;
    padding: 2rem 2rem;
    font-size: 10px;
    height: 160px;
    margin:10px 10px;
    box-shadow: 0 0 25px rgba(160, 77, 255, 0.5),
  inset 0 0 0px rgba(160, 77, 255, 0.3);
  line-height: 1.5;
  }

  .code {
    font-size: 12px;
    
  }

  .windowsButtons {
    top: 10px;
    left: 12px;
    gap: 6px;
  }

  .windowButton {
    width: 12px;
    height: 12px;
  }

  .cursor {
    width: 6px;
    height: 12px;
  }

  
}

@media (max-width: 480px) {
  .codeBox {
    padding: 2rem 1rem;
    font-size: 10px;
    line-height: 1.7;
  }

  .code {
    font-size: 14px;
  }

  .cursor {
    width: 5px;
    height: 10px;
  }
}


</style>


<template>
  <div v-if="showPreloader" class="preloader" :class="{ 'fade-out': finished }">
    <!-- TERMINAL BOX -->
    <div class="codeBox scale-up">
      <div class="windowsButtons">
        <span class="windowButton red"></span>
        <span class="windowButton yellow"></span>
        <span class="windowButton green"></span>
      </div>
      <pre>{{ displayedCode }} <span class="cursor"></span></pre>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const fullCode = `
kartal-desktop: console.log("☕ Making coffee");
kartal-desktop: console.log("💻 Compiling focus");
kartal-desktop: console.log("✅ Developer mode: ON");`;
const displayedCode = ref("");
const showPreloader = ref(true);
const finished = ref(false);

onMounted(() => {
  const totalDuration = 3600; 
  const typingSpeed = totalDuration / fullCode.length;
  let index = 0;
// TYPING CODE
  const type = () => {
    if (index < fullCode.length) {
      displayedCode.value += fullCode[index];
      index++;
      setTimeout(type, typingSpeed);
    } else {
      finished.value = true;
      setTimeout(() => {
        showPreloader.value = false;
      }, 2100); 
    }
  };
  type();
});
</script>

