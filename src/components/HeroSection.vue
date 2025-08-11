<template>
    <head>
        <link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css"
/>
    </head>
  <div class="infoBox">
    <div class="imageDeveloper">
      <img src="@/assets/halidkartal.jpg" alt="Alex" />
    </div>
    <div class="developerDescription">
      <h1>Hi, It's <span class="highlight">Kartal</span></h1>
      <h2>I'm Full-Stack Developer</h2>
      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Minus laborum dolores esse. Odit similique doloribus
        tenetur doloremque, sunt commodi in ipsa repudiandae debitis deleniti blanditiis quibusdam quaerat neque asperiores ea.
      </p>

      <!-- Ikone + Dugme u istom redu -->
      <div class="actionsRow">
        <div class="socialMedia">
          <a href="https://www.linkedin.com/in/tvoj-profil" target="_blank">
            <i class="fab fa-linkedin-in"></i>
          </a>
          <a href="https://github.com/tvoj-username" target="_blank">
            <i class="fab fa-github"></i>
          </a>
          <a href="https://www.facebook.com/tvoj-profil" target="_blank">
            <i class="fab fa-facebook-f"></i>
          </a>
        </div>
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
</script>

<style scoped>
.infoBox {
  display: flex;
  align-items: center;
  gap: 3rem;
  padding: 2rem;
  color: #fff;
  height: 80vh;
  font-family: 'Poppins', sans-serif;
  justify-content: center;
     flex-wrap: wrap;
}
.actionsRow {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-top: 30px;
  flex-wrap: wrap;
}
.imageDeveloper {
  position: relative;
  width: 300px;
  height: 400px;
  border-radius: 50%;
  overflow: hidden;
  background: radial-gradient(circle at center, #ff2e2e 0%, #000 70%);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  animation: pulse 3s infinite ease-in-out;
}

.imageDeveloper img {
  width: 100%;
  height: auto;
  object-fit: cover;
  mix-blend-mode: lighten;
}

.developerDescription {
  max-width: 500px;
  text-align: left;
}

.developerDescription h1 {
  font-size: 3rem;
  font-weight: 700;
}

.developerDescription h1 .highlight {
  color: #c75b63;
  animation: textGlow 2s infinite alternate ease-in-out;
}

.developerDescription h2 {
  font-size: 2rem;
  margin-top: 0.2rem;
}

.developerDescription p {
  margin-top: 1rem;
  font-size: 0.95rem;
  line-height: 1.5;
  color: #ccc;
}


.hireMeTopButton {
  position: relative;
  display: inline-block;
  padding: 3px;
  border-radius: 8px;
  z-index: 1;
}

.hireMeTopButton::before {
  content: '';
  position: absolute;
  inset: 0;
  background: conic-gradient(
    from 0deg,
    #ff0055,
    #ffcc00,
    #ff0055
  );
  border-radius: 10px;
  z-index: -1;
  animation: moveGradient 3s linear infinite;
  background-size: 200% 200%;
  padding: 2px;
  mask: 
    linear-gradient(#fff 0 0) content-box,
    linear-gradient(#fff 0 0);
  -webkit-mask: 
    linear-gradient(#fff 0 0) content-box,
    linear-gradient(#fff 0 0);
  mask-composite: exclude;
  -webkit-mask-composite: destination-out;
}

.hireMeTopButton a {
  display: block;
  background-color: #000;
  color: #fff;
  padding: 0.75rem 2rem;
  border-radius: 6px;
  font-weight: 600;
  text-decoration: none;
  position: relative;
  z-index: 1;
}

/* BUTTON ANIMATION */

@keyframes moveGradient {
  0% {
    background-position: 0% 50%;
  }
  100% {
    background-position: 360% 50%;
  }
}

.socialMedia {
  display: flex;
  gap: 20px;
  justify-content: center; /* Ikone u sredini */
  align-items: center;
  margin: 20px 0;
  margin-right:80px;
}

.socialMedia a {
  color: #555; /* Osnovna boja ikona */
  font-size: 24px;
  transition: color 0.3s ease, transform 0.3s ease;
  text-decoration: none;
}

.socialMedia a:hover {
  color: #0077b5; /* Plava LinkedIn boja, možeš promijeniti po želji */
  transform: scale(1.2);
}

/* Različite boje po platformama */
.socialMedia a:nth-child(1):hover {
  color: #0077b5; /* LinkedIn */
}

.socialMedia a:nth-child(2):hover {
  color: #333; /* GitHub crna */
}

.socialMedia a:nth-child(3):hover {
  color: #1877f2; /* Facebook plava */
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
    background: linear-gradient(45deg, #ff0000, #ff7300, #fffb00, #48ff00, #00ffd5, #002bff, #7a00ff, #ff00c8, #ff0000);
    position: absolute;
    top: -2px;
    left:-2px;
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

.glow-on-hover:active:after {
    background: transparent;
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

@keyframes glowing {
    0% { background-position: 0 0; }
    50% { background-position: 400% 0; }
    100% { background-position: 0 0; }
}




/* PICTURE PULSE */

@keyframes pulse {
  0% {
    box-shadow: 0 0 0px #3B1360;
  }
  50% {
    box-shadow: 0 0 25px #3B1360, 0 0 20px #3B1360;
  }
  100% {
    box-shadow: 0 0 0px #3B1360;
  }
}

/* NAME GLOW */

@keyframes textGlow {
  0% {
    text-shadow: 0 0 0px #c75b63;
  }
  50% {
    text-shadow: 0 0 10px #c75b63, 0 0 20px #c75b63, 0 0 30px #c75b63;
  }
  100% {
    text-shadow: 0 0 0px #c75b63;
  }
}

 /* RESPONSIVE DESIGN */

@media (max-width: 768px) {
  .infoBox {
    flex-direction: column;
    height: auto;
    text-align: center;
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
}

@media (max-width: 480px) {
  .imageDeveloper {
    width: 220px;
    height: 300px;
  }

  .developerDescription h1 {
    font-size: 2rem;
  }

  .developerDescription h2 {
    font-size: 1.5rem;
  }

  .developerDescription p {
    font-size: 0.9rem;
  }
}
</style>
