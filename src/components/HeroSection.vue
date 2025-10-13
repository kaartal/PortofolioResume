<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css');

.infoBox {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  padding: 2rem;
  color: #fff;
  font-family: 'Poppins', sans-serif;
  flex-wrap: wrap;
  margin-top: 100px;
  margin-bottom: 100px;
  height: 800px;
}

.imageDeveloper {
  position: relative;
  max-width: 400px;
  width: 100%;
  height: 800px;
  aspect-ratio: 5 / 6;
  z-index: 2;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;

  opacity: 0;
  transform: translateY(30px);
  animation: fadeInSlide 1.2s ease-out forwards;
  animation-delay: 0.3s; 
}

@keyframes fadeInSlide {
  to {
    opacity: 2;
    transform: translateY(-1);
  }
}


.imageDeveloper img {
  width: 100%;
  object-fit: contain;
  background-color: transparent;
  border-radius: 20px;
}

/*ROCKET ANIMATION */
.rocket-float {
  animation: rocketMove 5s ease-in-out infinite, rocketGlow 3s infinite alternate ease-in-out;
}

@keyframes rocketMove {
  0% {
    transform: translateY(0) rotate(-1deg);
  }
  50% {
    transform: translateY(-10px) rotate(1deg);
  }
  100% {
    transform: translateY(0) rotate(-1deg);
  }

}/* DEVELOPER INFO */
.fadeSection.visible {
  opacity: 1;
  pointer-events: auto;
}

.developerDescription {
  max-width: 600px;
  width: 100%;

}

.developerDescription h1 {
  font-size: 4rem;
  font-weight: 700;
  font-family: 'Orbitron';
}

.developerDescription h1 .highlight {
  color: #A04DFF;
  animation: textGlow 2s infinite alternate ease-in-out;
  
}

.developerDescription h2 {
  font-size: 2.5rem;
  margin-top: 0.2rem;
  font-family: 'Orbitron', sans-serif;
}

.developerDescription p {
  margin-top: 1rem;
  font-size: 1rem;
  line-height: 1.6;
  color: #ccc;
  font-weight: 500; 
font-size: 1.2rem; 
letter-spacing: 1px; 
line-height: 1.6; 
font-family: 'Orbitron', sans-serif;
}

.actionsRow {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-top: 30px;
  flex-wrap: wrap;
  z-index: 1;
}

.resumeButton {
  text-align: center;
}

.glowHover {
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
  font-family: 'Orbitron', sans-serif;
}

.glowHover:before {
  content: '';
  background: linear-gradient(
    45deg,
    #ff0000,
    #ff7300,
    #fffb00,
    #48ff00,
    #00ffd5,
    #002bff,
    #7a00ff,
    #ff00c8,
    #ff0000
  );
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
  transition: opacity 0.3s ease-in-out;
  border-radius: 10px;
}

.glowHover:hover:before {
  opacity: 1;
}

.glowHover:active {
  color: #000;
}

.glowHover:after {
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

.flySocial {
  position: fixed;
  top: 40%;
  left:10px;
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

@keyframes textGlow {
  0% {
    text-shadow: 0 0 0px #A04DFF;
  }
  50% {
    text-shadow: 0 0 2px #A04DFF, 0 0 20px #A04DFF, 0 0 4px #A04DFF;
  }
  100% {
    text-shadow: 0 0 0px #A04DFF;
  }
}

/* RESPONSIVE DESIGN */
@media (max-width: 1024px) {
  .infoBox {
    padding-top: 8rem;
    margin-top: 40px;
    flex-direction: column;
    text-align: center;
    height: auto;
    gap: 2rem;
  }

  .actionsRow {
    text-align: center;
    justify-content: center;
  }

  .developerDescription {
    max-width: 90%;
    text-align: center;
    margin-top:-80px;
    margin-bottom:-40px;
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

    .flySocial {
    left: 4px;  }
}

@media (max-width: 768px) {
  .flySocial {
    display: none;
  }

  .infoBox {
  margin-top:-170px;
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
</style>

<template>

<div id="about"></div>

  <!-- SOCIAL MEDIA FIXED LINKS -->
  <div class="flySocial">
    <!-- LINKEDIN PROFILE -->
    <a href="https://linkedin.com/in/halidkartal" target="_blank">
      <i class="fab fa-linkedin-in"></i>
    </a>
    <!-- GITHUB PROFILE -->
    <a href="https://github.com/kaartal" target="_blank">
      <i class="fab fa-github"></i>
    </a>
    <!-- FACEBOOK PROFILE -->
    <a href="https://www.facebook.com/halid.kartal.2025" target="_blank">
      <i class="fab fa-facebook-f"></i>
    </a>
  </div>

  <!-- DEVELOPER INFO -->
  <div class="infoBox">
    <!-- ROCKET PICTURE -->
    <div class="imageDeveloper fade-section" :class="{ visible: showImage }">
      <img
        :class="['rocket-img', { 'rocket-enter': rocketVisible, 'rocket-float': rocketVisible }]"
        :src="rocketImg"
        alt="Developer Image"
      />
    </div>

    <!-- DESCRIPTION -->
    <div class="developerDescription">
      <h1 class="fadeSection" :class="{ visible: showTitle }">
        Hi, I'm <span class="highlight">Kartal</span>
      </h1>

      <h2 class="fadeSection" :class="{ visible: showTitle }">
        I'm a Full-Stack Software Engineer
      </h2>

      <p class="fadeSection" :class="{ visible: showText }">
        Innovative Full Stack Developer passionate about creating seamless and impactful app solutions.
        Passionate about using modern technologies to solve real-world problems.
      </p>

      <div class="actionsRow fadeSection" :class="{ visible: showButton }">
        <div class="resumeButton">
           <a href="/resume halidkartal.pdf" download>
  <button class="glowHover">
    CV Coming Soon 🚀
  </button>
</a>

        </div>
      </div>
    </div>

  </div>

</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import rocketImg from '@/assets/rocket.png'

const showImage = ref(false)
const showTitle = ref(false)
const showText = ref(false)
const showButton = ref(false)
const rocketVisible = ref(false)

// SHOW TEXT 1s, 1s, 1s, 0.5s
onMounted(() => {
  setTimeout(() => {
    showImage.value = true
    rocketVisible.value = true
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

const scrollArrow = ref(null)

const handleScroll = () => {
  if (window.scrollY > 10) {
    scrollArrow.value.style.opacity = '0'
  } else {
    scrollArrow.value.style.opacity = '1'
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

