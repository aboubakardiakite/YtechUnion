<template>
  <section id="contact" class="contact-section">
    <div class="contact-container">
      <div class="contact-info">
        <h2>Contactez-nous</h2>
        <form @submit.prevent="submitForm" class="contact-form">
          <div class="form-group">
            <input 
              type="text" 
              v-model="formData.name" 
              placeholder="Votre nom"
              required
            >
          </div>
          <div class="form-group">
            <input 
              type="email" 
              v-model="formData.email" 
              placeholder="Votre email"
              required
            >
          </div>
          <div class="form-group">
            <textarea 
              v-model="formData.message" 
              placeholder="Votre message"
              required
            ></textarea>
          </div>
          <button type="submit" class="submit-btn">SOUMETTRE</button>
        </form>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      // Ici, vous pouvez ajouter la logique pour envoyer le formulaire
      console.log('Formulaire soumis:', this.formData)
      // Réinitialiser le formulaire
      this.formData = {
        name: '',
        email: '',
        message: ''
      }
    }
  }
}
</script>

<style scoped>
.contact-section {
  padding: 5rem 2rem;
  background-color: #1a1a1a;
  color: white;
}

.contact-container {
  max-width: 800px;
  margin: 0 auto;
}

h2 {
  text-align: center;
  margin-bottom: 3rem;
  font-size: 2.5rem;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 1rem;
  border: none;
  border-radius: 4px;
  background-color: #333;
  color: white;
}

.form-group textarea {
  height: 150px;
  resize: vertical;
}

.submit-btn {
  background-color: #FF6B00;
  color: white;
  padding: 1rem 2rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.3s ease;
}

.submit-btn:hover {
  background-color: #ff8533;
}

@media (max-width: 768px) {
  .contact-section {
    padding: 3rem 1rem;
  }

  .contact-container {
    width: 100%;
    padding: 0 1rem;
  }

  h2 {
    font-size: 2rem;
  }

  .form-group input,
  .form-group textarea {
    padding: 0.8rem;
  }

  .submit-btn {
    width: 100%;
  }
}
</style> 