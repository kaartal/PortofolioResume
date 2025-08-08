<template>
  <div class="footerBox">
    <footer class="footer">
      <h2 class="footerTitle">Contact me</h2>
      <a href="mailto:halidkartal09@gmail.com" class="email">halidkartal09@gmail.com</a>
<!-- SOCIAL LINKS -->
      <div class="socialLinks">
        <a href="https://linkedin.com/in/halidkartal" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
        <a href="https://www.facebook.com/tvoj-profil" target="_blank"><i class="fab fa-facebook"></i></a>
        <a href="https://github.com/kaartal" target="_blank"><i class="fab fa-github"></i></a>
      </div>
      <div class="crafted">
        <span>Created by me</span><br />
        <p>Halid Kartal</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
</script>

<style scoped>
.footerBox {
  position: relative;
  overflow: hidden;
  height: auto; 
  background-color: black;
  clip-path: polygon(0 30%, 100% 0, 130% 100%, 0% 100%);
}

.footer {
  position: relative;
  background-color: black;
  color: white;
  text-align: center;
  padding: 40px 20px;
  font-family: 'Courier New', monospace;
  z-index: 2;
  margin-top: 180px;
}

.footerTitle {
  font-size: 2.4em;
  background-color: white;
  color: black;
  display: inline-block;
  padding: 5px 10px;
  margin-bottom: 20px;
  clip-path: polygon(0 15%, 100% 0, 1030% 100%, 0% 100%);
}

.email {
  display: block;
  font-size: 1.4em;
  color: white;
  margin-bottom: 40px;
  text-decoration: none;
  word-wrap: break-word;
}

.socialLinks {
  margin: 20px 0;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}

.socialLinks a {
  color: white;
  font-size: 2em;
  transition: color 0.3s ease;
}

.socialLinks a:hover {
  color: gray;
}

.crafted {
  margin-top: 30px;
  font-size: 1em;
}

/* TABLET RESPONSIVE */
@media (max-width: 1024px) {
  .footerBox {
    clip-path: polygon(0 20%, 100% 0, 1030% 100%, 0% 100%);
  }
}

/* MOBILE RESPONSIVE */
@media (max-width: 600px) {
  .footerBox {
    clip-path: polygon(0 15%, 100% 0, 1030% 100%, 0% 100%);
  }
}

/* SMALL SCREEN DESIGN RESPONSIVE */
@media (max-width: 768px) {
  .footerTitle {
    font-size: 1.8em;
    padding: 4px 8px;
  }

  .email {
    font-size: 1.1em;
    margin-bottom: 30px;
  }

  .socialLinks a {
    font-size: 1.5em;
  }

  .crafted {
    font-size: 0.9em;
  }
}

@media (max-width: 480px) {
  .footer {
    padding: 30px 15px;
  }

  .footerTitle {
    font-size: 1.5em;
  }

  .email {
    font-size: 1em;
  }

  .socialLinks {
    gap: 15px;
  }

  .socialLinks a {
    font-size: 1.3em;
  }
}

</style>
