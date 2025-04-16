<template>
  <section id="accueil" class="hero">
    <div class="hero-image"></div>
    <div class="hero-content">
      <h1>CONSTRUIRE TON <span>SITE WEB</span></h1>
      <p>Transformez votre vision en réalité avec des solutions web sur mesure et innovantes.</p>
      <a href="#contact" class="cta-button">
        Démarrer votre projet
        <i class="fas fa-arrow-right"></i>
      </a>
    </div>
  </section>
</template>

<script>
import imageHero from '../assets/images/Hero.png'

export default {
  name: 'Hero'
}
</script>

<style scoped>
.hero {
  height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  position: relative;
  overflow: hidden;
}

.hero-image {
  background-image: url('../assets/images/Hero.png');
  background-size: cover;
  background-position: center;
  height: 100%;
  position: relative;
}

.hero-image::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.3);
}

.hero-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 2rem 4rem;
  background-color: #1a1a1a;
  color: white;
  position: relative;
}

.hero-content::before {
  content: '';
  position: absolute;
  top: 0;
  left: -50px;
  height: 100%;
  width: 100px;
  background: #1a1a1a;
  transform: skewX(-5deg);
}

.hero-content h1 {
  font-size: 3.5rem;
  margin-bottom: 1.5rem;
  line-height: 1.2;
  font-weight: 700;
}

.hero-content span {
  color: #FFD700;
  display: block;
}

.hero-content p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  color: #f0f0f0;
  line-height: 1.6;
  max-width: 600px;
}

.cta-button {
  background-color: #FFD700;
  color: #1a1a1a;
  border: none;
  padding: 1rem 2rem;
  font-size: 1.1rem;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s ease;
  width: fit-content;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.8rem;
  font-weight: 600;
}

.cta-button i {
  transition: transform 0.3s ease;
}

.cta-button:hover {
  background-color: #fff;
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
}

.cta-button:hover i {
  transform: translateX(5px);
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

  .hero-content::before {
    display: none;
  }

  .hero-content h1 {
    font-size: 2rem;
  }

  .hero-content p {
    font-size: 1rem;
    text-align: center;
  }
}
</style> 