<style scoped>
.footerSectionDesign {
  position: relative;
  overflow: hidden;
  height: auto; 
  background-color: black;
  clip-path: polygon(0 20%, 100% 0, 100% 100%, 0% 100%);
}

.footerMainBox {
  position: relative;
  background-color: black;
  color: white;
  text-align: center;
  padding: 80px 40px;
  font-family: 'Courier New', monospace;
  z-index: 1;
  margin-top: 80px;
}

.footerTitleText {
  font-size: 2.4em;
  background-color: white;
  color: black;
  display: inline-block;
  padding: 5px 10px;
  margin-bottom: 20px;
  clip-path: polygon(0 15%, 100% 0, 1030% 100%, 0% 100%);
}

.emailTextDesign {
  display: block;
  font-size: 1.8em;
  color: white;
  margin-bottom: 40px;
  text-decoration: none;
  word-wrap: break-word;
}

.socialLinksSectionDesign {
  margin: 20px 0;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}

.socialLinksText a {
  color: white;
  font-size: 2em;
  transition: color 0.3s ease;
  width:40px;
  
}
.socialLinksSectionDesign a i {
  color: white;
  font-size: 2em;
  transition: color 0.3s ease;
}

.socialLinksSectionDesign a i:hover {
  color: gray;
}

.socialLinksText a:hover {
  color: gray;
}

.craftedFromDeveloper {
  margin-top: 30px;
  font-size: 1.3em;
}

/* TABLET RESPONSIVE */
@media (max-width: 1024px) {

  .footerSectionDesign {
  margin-top: 40px;
}

  .footerMainBox {
    clip-path: polygon(0 20%, 100% 0, 1030% 100%, 0% 100%);
  }
}

/* MOBILE RESPONSIVE */
@media (max-width: 600px) {
  .footerMainBox {
    clip-path: polygon(20 15%, 1020% 20, 100% 100%, 22% 100%);
  }
}

/* SMALL SCREEN DESIGN RESPONSIVE */
@media (max-width: 768px) {
 
  .footerSectionDesign {
  margin-top: 30px;
  clip-path: polygon(0 20%, 145% 0, 127% 100%, 0% 100%);
  }
  .footerTitleText {
    font-size: 2.4em;
    padding: 4px 8px;
  }

  .emailTextDesign {
    font-size: 1.4em;
    margin-bottom: 30px;
  }

  .socialLinksText a {
    font-size: 1.5em;
  }

  .craftedFromDeveloper {
    font-size: 1.1em;
    padding:10px 40px;
  }
}

@media (max-width: 480px) {

   
  .footerSectionDesign {
    padding: 30px 15px;
  }

  .footerTitleText {
    font-size: 1.5em;
  }

  .emailTextDesign {
    font-size: 1.2;
  }

  .socialLinksText {
    gap: 15px;
  }

  .socialLinksText a {
    font-size: 1.3em;
  }
}
</style>

<template>
  <div class="footerSectionDesign">
    <footer class="footerMainBox">
      <h2 class="footerTitleText">Contact me</h2>
      <a href="mailto:halidkartal09@gmail.com" class="emailTextDesign">halidkartal09@gmail.com</a>

      <!-- SOCIAL LINKS LINKEDIN, FACEBOOK, GITHUB -->
      <div class="socialLinksSectionDesign">
        <a href="https://linkedin.com/in/halidkartal" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
        <a href="https://www.facebook.com/halid.kartal.2025" target="_blank"><i class="fab fa-facebook"></i></a>
        <a href="https://github.com/kaartal" target="_blank"><i class="fab fa-github"></i></a>
      </div>

      <!-- CRAFTED BY DEVELOPER SIGNATURE -->
     <div class="craftedFromDeveloper">
  <span>Created by me</span><br />
  <svg xmlns='@/assets/halidkartal.png' viewBox="0 0 600 120" width="180" height="50">
    <text x="10" y="130" 
          font-family="Brush Script MT, cursive" 
          font-size="130" 
          fill="white">
      Halid Kartal
    </text>
  </svg>
</div>
</footer>
</div>
</template>


