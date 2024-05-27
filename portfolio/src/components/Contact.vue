<!-- src/components/Contact.vue -->
<template>
  <div class="contact">
    <h1>Contactez-moi</h1>
    <form @submit.prevent="sendEmail" v-if="!formSubmitted">
      <div class="form-group">
        <label for="name">Nom:</label>
        <input type="text" id="name" v-model="form.name" required>
      </div>
      <div class="form-group">
        <label for="subject">Objet:</label>
        <input type="text" id="subject" v-model="form.subject" required>
      </div>
      <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="form.email" required>
      </div>
      <div class="form-group">
        <label for="message">Message:</label>
        <textarea id="message" v-model="form.message" required></textarea>
      </div>
      <button type="submit" :disabled="isSending">Envoyer</button>
    </form>
    <p v-else>Merci pour votre message. Nous vous répondrons dès que possible.</p>
  </div>
</template>

<script>
import emailjs from 'emailjs-com';

export default {
  name: 'Contact',
  data() {
    return {
      form: {
        name: '',
        subject: '',
        email: '',
        message: ''
      },
      formSubmitted: false,
      isSending: false
    };
  },
  methods: {
    sendEmail() {
      if (this.form.name && this.form.subject && this.form.email && this.form.message) {
        this.isSending = true;
        const templateParams = {
          name: this.form.name,
          email: this.form.email,
          subject: this.form.subject,
          message: this.form.message
        };

        emailjs.send('service-reception', 'template_lc41lzc', templateParams, 'RWeueEn7v9If_faEc')
          .then((response) => {
            console.log('Email sent successfully!', response.status, response.text);
            this.formSubmitted = true;
          }, (error) => {
            console.error('Failed to send email.', error);
            alert('L\'envoi du message a échoué. Veuillez réessayer.');
          })
          .finally(() => {
            this.isSending = false;
            setTimeout(() => {
              this.formSubmitted = false;
              this.form.name = '';
              this.form.subject = '';
              this.form.email = '';
              this.form.message = '';
            }, 10000); // 3 seconds delay to reset the form
          });
      } else {
        alert('Veuillez remplir tous les champs.');
      }
    }
  }
};
</script>

<style scoped>
.contact {
  color: white;
  padding: 1rem;
  max-width: 600px;
  margin: 0 auto;
  text-align: center; /* Centre le titre et le formulaire */
}

.form-group {
  margin-bottom: 1rem;
  text-align: left; /* Assure que les labels et les champs de saisie sont alignés à gauche */
}

label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: bold;
}

input, textarea {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 0.75rem 1.5rem;
  background-color: #007BFF;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin-top: 1rem; /* Espace au-dessus du bouton */
  font-size: 18px;
}

button:disabled {
  background-color: #cccccc; /* Change la couleur du bouton lorsqu'il est désactivé */
}

button:hover:enabled {
  background-color: #0056b3;
}
</style>
