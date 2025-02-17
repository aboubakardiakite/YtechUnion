<template>
  <section id="clients" class="clients-section">
    <h2>Nos clients</h2>
    <div class="clients-grid">
      <div v-for="(image, i) in clientImages" :key="i" class="client-box">
        <img :src="image" :alt="`Client ${i + 1}`">
      </div>
    </div>
  </section>
</template>

<script>
import { images } from '../assets/images'

export default {
  name: 'Clients',
  data() {
    return {
      clientImages: images.clients
    }
  }
}
</script>

<style scoped>
.clients-section {
  padding: 5rem 2rem;
  background-color: #f9f9f9;
}

h2 {
  text-align: center;
  margin-bottom: 3rem;
  font-size: 2.5rem;
  color: #333;
}

.clients-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.client-box {
  background: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s ease;
}

.client-box:hover {
  transform: translateY(-5px);
}

.client-box img {
  max-width: 100%;
  height: auto;
}

@media (max-width: 768px) {
  .clients-section {
    padding: 3rem 1rem;
  }

  h2 {
    font-size: 2rem;
  }

  .clients-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .client-box {
    padding: 1rem;
  }
}

@media (max-width: 480px) {
  .clients-grid {
    grid-template-columns: 1fr;
  }
}
</style> 