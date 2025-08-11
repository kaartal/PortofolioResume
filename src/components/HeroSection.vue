<template>
  <!-- SOCIAL MEDIA FIXED LINKS -->
  <div class="flySocial">
    <a href="https://linkedin.com/in/halidkartal" target="_blank">
      <i class="fab fa-linkedin-in"></i>
    </a>
    <a href="https://github.com/kaartal" target="_blank">
      <i class="fab fa-github"></i>
    </a>
    <a href="https://www.facebook.com/tvoj-profil" target="_blank">
      <i class="fab fa-facebook-f"></i>
    </a>
  </div>

  <!-- DEVELOPER INFO -->
  <div class="infoBox">
    <!-- PICTURE -->
    <div class="imageDeveloper fade-section" :class="{ visible: showImage }">

    </div>

    <!-- DESCRIPTION -->
    <div class="developerDescription">
      <h1 class="fade-section" :class="{ visible: showTitle }">
        Hi, It's <span class="highlight">Kartal</span>
      </h1>

      <h2 class="fade-section" :class="{ visible: showTitle }">
        I'm Full-Stack Developer
      </h2>

      <p class="fade-section" :class="{ visible: showText }">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit similique doloribus tenetur doloremque.
        Minus laborum dolores esse.
      </p>

      <div class="actionsRow fade-section" :class="{ visible: showButton }">
        <div class="resume-button">
          <a href="/test.pdf" download>
            <button class="glow-on-hover">
              📄 Download Resume
            </button>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'

const showImage = ref(false)
const showTitle = ref(false)
const showText = ref(false)
const showButton = ref(false)

onMounted(() => {
  setTimeout(() => {
    showImage.value = true
    setTimeout(() => {
      showTitle.value = true
      setTimeout(() => {
        showText.value = true
        setTimeout(() => {
          showButton.value = true
        }, 1000)
      }, 1000)
    }, 1000)
  }, 500)
})
</script>


<style scoped>@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css');

.infoBox {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  padding: 2rem;
  color: #fff;
  font-family: 'Poppins', sans-serif;
  flex-wrap: wrap;
  margin-top:250px;
  margin-bottom:200px;
}

.imageDeveloper {
  position: relative;
  max-width: 400px;
  width: 100%;
  aspect-ratio: 5 / 6;
  z-index: 1;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  animation: pulse 3s infinite ease-in-out;
}

.imageDeveloper img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  mix-blend-mode: lighten;
  border-radius: 20px;
}

.developerDescription {
  max-width: 500px;
  width: 100%;
}

.developerDescription h1 {
  font-size: 3rem;
  font-weight: 700;
}

.developerDescription h1 .highlight {
  color: #A04DFF;
  animation: textGlow 2s infinite alternate ease-in-out;
}

.developerDescription h2 {
  font-size: 2rem;
  margin-top: 0.2rem;
}

.developerDescription p {
  margin-top: 1rem;
  font-size: 1rem;
  line-height: 1.6;
  color: #ccc;
}

.actionsRow {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-top: 30px;
  flex-wrap: wrap;
  z-index: 1;
}

.resume-button {
  text-align: center;
}

.glow-on-hover {
  width: 220px;
  height: 50px;
  border: none;
  outline: none;
  color: #fff;
  background: #111;
  cursor: pointer;
  position: relative;
  z-index: 0;
  border-radius: 10px;
  font-size: 18px;
  font-weight: bold;
  transition: color 0.3s ease;
}

.glow-on-hover:before {
  content: '';
  background: linear-gradient(45deg, #ff0000, #ff7300, #fffb00, #48ff00,
              #00ffd5, #002bff, #7a00ff, #ff00c8, #ff0000);
  position: absolute;
  top: -2px;
  left: -2px;
  background-size: 400%;
  z-index: -1;
  filter: blur(5px);
  width: calc(100% + 4px);
  height: calc(100% + 4px);
  animation: glowing 20s linear infinite;
  opacity: 0;
  transition: opacity .3s ease-in-out;
  border-radius: 10px;
}

.glow-on-hover:hover:before {
  opacity: 1;
}

.glow-on-hover:active {
  color: #000;
}

.glow-on-hover:after {
  z-index: -1;
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  background: #111;
  left: 0;
  top: 0;
  border-radius: 10px;
}

.fade-section {
  opacity: 0;
  transition: opacity 2s ease-in-out;
  pointer-events: none;
}

.fade-section.visible {
  opacity: 1;
  pointer-events: auto;
}

.flySocial {
  position: fixed;
  top: 40%;
  left: 10px;
  display: flex;
  flex-direction: column;
  gap: 20px;
  z-index: 10;
  animation: floatY 3s ease-in-out infinite;
}

.flySocial a {
  color: #555;
  font-size: 22px;
  transition: transform 0.3s ease, color 0.3s ease;
}

.flySocial a:hover {
  transform: scale(1.3);
  color: #A04DFF;
}

@keyframes glowing {
  0% { background-position: 0 0; }
  50% { background-position: 400% 0; }
  100% { background-position: 0 0; }
}

@keyframes pulse {
  0% { box-shadow: 0 0 0px #3B1360; }
  50% { box-shadow: 0 0 25px #3B1360, 0 0 20px #3B1360; }
  100% { box-shadow: 0 0 0px #3B1360; }
}

@keyframes textGlow {
  0% { text-shadow: 0 0 0px #A04DFF; }
  50% { text-shadow: 0 0 10px #A04DFF, 0 0 20px #A04DFF, 0 0 30px #A04DFF; }
  100% { text-shadow: 0 0 0px #A04DFF; }
}

@keyframes floatY {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
  100% { transform: translateY(0px); }
}

/* ---------- RESPONSIVE ---------- */
@media (max-width: 1024px) {
  .infoBox {
    flex-direction: column;
    text-align: center;
    height: auto;
    gap: 2rem;
  }

  .developerDescription {
    max-width: 90%;
    text-align: center;
  }

  .developerDescription h1 {
    font-size: 2.5rem;
  }

  .developerDescription h2 {
    font-size: 1.8rem;
  }

  .developerDescription p {
    font-size: 1rem;
  }
}

@media (max-width: 480px) {
  .imageDeveloper {
    max-width: 280px;
    aspect-ratio: 5 / 7;
  }

  .developerDescription h1 {
    font-size: 2rem;
  }

  .developerDescription h2 {
    font-size: 1.4rem;
  }

  .developerDescription p {
    font-size: 0.9rem;
  }

  .glow-on-hover {
    width: 90%;
    font-size: 16px;
  }
}
@media (max-width: 768px) {
  .infoBox {
    padding-top: 8rem;
  }

  .flySocial {
display:none;
}

}

@media (max-width: 1024px) {
  .infoBox {
    padding-top: 8rem;
  }
}


</style>
