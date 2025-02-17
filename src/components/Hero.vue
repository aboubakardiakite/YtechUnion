<template>
  <section id="accueil" class="hero">
    <div class="hero-image" :style="{ backgroundImage: `url(${heroBg})` }"></div>
    <div class="hero-content">
      <h1>CONSTRUIRE TON <span>SITE WEB</span></h1>
      <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
      <button class="cta-button">Commencer un projet</button>
    </div>
  </section>
</template>

<script>
import { images } from '../assets/images'

export default {
  name: 'Hero',
  data() {
    return {
      heroBg: images.heroBg
    }
  }
}
</script>

<style scoped>
.hero {
  height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.hero-image {
  background-size: cover;
  background-position: center;
  height: 100%;
}

.hero-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 2rem 4rem;
  background-color: #1a1a1a;
  color: white;
}

.hero-content h1 {
  font-size: 3.5rem;
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.hero-content span {
  color: #FF6B00;
  display: block;
}

.hero-content p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  color: #ccc;
  line-height: 1.6;
}

.cta-button {
  background-color: #FF6B00;
  color: white;
  border: none;
  padding: 1rem 2rem;
  font-size: 1.1rem;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  width: fit-content;
}

.cta-button:hover {
  background-color: #ff8533;
}

@media (max-width: 1024px) {
  .hero-content {
    padding: 2rem;
  }

  .hero-content h1 {
    font-size: 2.5rem;
  }
}

@media (max-width: 768px) {
  .hero {
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr;
  }

  .hero-content {
    text-align: center;
    align-items: center;
  }

  .hero-content h1 {
    font-size: 2rem;
  }

  .hero-content p {
    font-size: 1rem;
  }
}
</style> 