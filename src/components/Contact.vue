<script setup>
import { ref } from 'vue'
import emailjs from '@emailjs/browser'

const name = ref('')
const email = ref('')
const message = ref('')
const success = ref(false)
const error = ref(false)

const sendMail = async () => {
  try {
    const templateParams = {
      from_name: name.value,
      from_email: email.value,
      message: message.value,
    }
    console.log(templateParams)

    await emailjs.send(
        import.meta.env.VITE_EMAILJS_SERVICE_ID,
        import.meta.env.VITE_EMAILJS_TEMPLATE_ID,
        templateParams,
        import.meta.env.VITE_EMAILJS_PUBLIC_KEY
    )

    success.value = true
    name.value = ''
    email.value = ''
    message.value = ''


    setTimeout(() => {
      success.value = false
    }, 4000)
  } catch (err) {
    console.error(err)
    error.value = true

    setTimeout(() => {
      error.value = false
    }, 4000)
  }
}
</script>

<template>
  <section id="contact" class="contact-section">
    <h2>Contactez-moi</h2>
    <p>N’hésitez pas à me laisser un message, je vous répondrai dès que possible.</p>

    <form @submit.prevent="sendMail" class="contact-form">
      <div class="form-group">
        <label for="name">Nom</label>
        <input type="text" id="name" v-model="name" placeholder="Votre nom" required />
      </div>

      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" v-model="email" placeholder="Votre email" required />
      </div>

      <div class="form-group">
        <label for="message">Message</label>
        <textarea id="message" v-model="message" rows="5" placeholder="Votre message..." required></textarea>
      </div>

      <button type="submit" class="btn-submit">Envoyer</button>

      <p v-if="success" class="success-msg">✅ Message envoyé avec succès !</p>
      <p v-if="error" class="error-msg">❌ Une erreur est survenue. Réessayez plus tard.</p>
    </form>
  </section>
</template>

<style scoped>
.contact-section {
  background: linear-gradient(135deg, #0a0a23, #1c1c46);
  color: #fff;
  padding: 80px 20px;
  text-align: center;
  font-family: 'Poppins', sans-serif;
  margin-top: 50px;
}

.contact-section h2 {
  color: #00d1ff;
  font-size: 2rem;
  margin-bottom: 10px;
}

.contact-section p {
  color: #dcdcdc;
  margin-bottom: 40px;
}

.contact-form {
  max-width: 600px;
  margin: 0 auto;
  background: rgba(255, 255, 255, 0.05);
  padding: 40px 30px;
  border-radius: 15px;
  box-shadow: 0 0 15px rgba(0, 209, 255, 0.1);
  backdrop-filter: blur(6px);
}

.form-group {
  margin-bottom: 25px;
  text-align: left;
}

label {
  display: block;
  color: #00d1ff;
  margin-bottom: 8px;
  font-weight: 500;
}

input,
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.1);
  color: #fff;
  font-size: 1rem;
  transition: all 0.3s ease;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #00d1ff;
  box-shadow: 0 0 10px #00d1ff;
}

.btn-submit {
  background: #00d1ff;
  color: #0a0a23;
  border: none;
  padding: 12px 25px;
  font-size: 1rem;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn-submit:hover {
  transform: scale(1.05);
  box-shadow: 0 0 15px #00d1ff;
  background: #03b8e0;
}

@media (max-width: 768px) {
  .contact-form {
    padding: 30px 20px;
  }
}
</style>