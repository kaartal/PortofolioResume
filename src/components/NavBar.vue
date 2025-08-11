<template>
    <section id="home">
  <nav class="navbarBox">
    <div class="logoPic"> 
      <span class="nameDeveloper">HK</span>
    </div>
    <ul class="navigationLinks">
      <li><a href="#home">Home</a></li>
      <li><a href="#">Education</a></li>
      <li><a href="#">Projects</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
    <div class="hireMeTopButton">
      <a href="#">Let's talk</a>
    </div>
  </nav>
  </section>
</template>

<script setup>
</script>
<style scoped>
.navbarBox {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 40px;
  background-color: transparent;
  flex-wrap: wrap;

}

.logoPic .nameDeveloper {
  font-size: 36px;
  font-weight: 800;
  background: linear-gradient(90deg, #A04DFF, #00B4FF);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  cursor: default;
  user-select: none;
}

.navigationLinks {
  list-style: none;
  display: flex;
  gap: 35px;
  margin: 0;
  padding: 0;
  flex-wrap: wrap;
    margin-top:20px;
}

.navigationLinks li a {
  text-decoration: none;
  color: white;
  font-weight: 600;
  font-size: 18px;
  transition: color 0.3s ease;
  position: relative;
  margin-top: 5px;
}

.navigationLinks li a::after {
  content: '';
  display: block;
  width: 0;
  height: 2px;
  background: #A04DFF;
  transition: width 0.5s;
  position: absolute;
  bottom: -3px;
  left: 0;
}

.navigationLinks li a:hover {
  color: #A04DFF;
}

.navigationLinks li a:hover::after {
  width: 100%;
}

.hireMeTopButton {
  position: relative;
  display: inline-block;
  padding: 3px;
  border-radius:24px;
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
  border-radius: 24px;
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

/* Dugme */
.hireMeTopButton a {
  display: block;
  color: #fff;
  padding: 0.75rem 2rem;
  border-radius: 24px;
  font-weight: 600;
  text-decoration: none;
  position: relative;
  z-index: 1;
}

/* Animacija */
@keyframes moveGradient {
  0% {
    background-position: 0% 50%;
  }
  100% {
    background-position: 360% 50%;
  }
}



/* Responsive - Mobile */
@media (max-width: 768px) {
  .navbarBox {
    padding: 15px 20px;
    justify-content: center;
    gap: 15px;
  }

  .navigationLinks {
    width: 100%;
    justify-content: center;
    gap: 20px;
    margin-top: 10px;
  }

  .hireMeTopButton {
    order: 3;
    width: 100%;
    text-align: center;
    margin-top: 15px;
  }

  .hireMeTopButton a {
    display: inline-block;
    width: 150px;
  }
}

/* Responsive - Small mobile */
@media (max-width: 480px) {
  .logoPic .nameDeveloper {
    font-size: 22px;
  }

  .navigationLinks li a {
    font-size: 14px;
    gap: 10px;
  }

  .hireMeTopButton a {
    width: 100%;
    padding: 12px 0;
  }
}
</style>
