<style scoped>
.contactSectionDeveloperMessage {
  padding: 20px 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 90vh;
}

.contactContainerDeveloperMessage {
  display: flex;
  flex-direction: column;
  align-items: center;
  backdrop-filter: blur(15px);
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.15);
  border-radius: 24px;
  box-shadow: 0 0 25px rgba(160, 77, 255, 0.1);
  max-width: 480px;
  width: 100%;
  padding: 50px 50px;
  transition: transform 0.7s ease, box-shadow 0.4s ease;
}

.contactContainerDeveloperMessage:hover {
  transform: translateY(-1px);
  box-shadow: 0 0 35px rgba(160, 77, 255, 0.15);
}

.contactFormMessage {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.contactFormMessage h2 {
  font-size: 2rem;
  text-align: center;
  color: #fff;
  letter-spacing: 1px;
  margin-bottom: 10px;
  font-family: 'Orbitron', 'Poppins';
}

.contactFormMessage .highlight {
  color: #A04DFF;
}

.contactFormMessage input,
.contactFormMessage textarea {
  padding: 14px 16px;
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  background: rgba(255, 255, 255, 0.05);
  color: #fff;
  font-size: 1rem;
  transition: all 0.3s ease;
  font-family: 'Orbitron', 'Poppins';
}

.contactFormMessage input::placeholder,
.contactFormMessage textarea::placeholder {
  color: rgba(255, 255, 255, 0.5);
}

.contactFormMessage input:focus,
.contactFormMessage textarea:focus {
  border-color: #A04DFF;
  box-shadow: 0 0 10px rgba(160, 77, 255, 0.4);
  background: rgba(255, 255, 255, 0.08);
}

.contactFormMessage button {
  padding: 15px;
  background: linear-gradient(135deg, #A04DFF, #4a10ff);
  color: #fff;
  border: none;
  border-radius: 12px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  font-family: 'Orbitron', 'Poppins';
}

.contactFormMessage button:hover {
  box-shadow: 0 0 20px rgba(160, 77, 255, 0.2);
}

@media (max-width: 600px) {
  .contactContainerDeveloperMessage {
    padding: 30px 20px;
  }
}
</style>

<template>
  <div class="contactSectionDeveloperMessage">
    <div class="contactContainerDeveloperMessage">
      <form
        action="https://getform.io/f/apjzexoa"
        method="POST"
        class="contactFormMessage">
        <h2>Get In <span class="highlight">Touch</span></h2>
        <input type="text" name="name" placeholder="Name" required />
        <input type="email" name="email" placeholder="Email" required />
        <textarea name="message" placeholder="Message" rows="5" required></textarea>
        <button type="submit">Submit ✈</button>
      </form>
    </div>
  </div>
</template>
