<template>
  <section id="qui-sommes-nous" class="about-section">
    <div class="about-content">
      <div class="about-image">
        <img :src="teamImage" alt="YTECH TEAM">
      </div>
      <div class="about-text">
        <h2>YTECH TEAM</h2>
        <p>Nous sommes une équipe dynamique de professionnels passionnés par le développement web, l'innovation et le marketing digital.</p>
        <p>Notre mission est de fournir des solutions web sur mesure qui aident nos clients à prospérer dans le monde numérique en constante évolution.</p>
        <p>Grâce à notre expertise, nous créons des sites web modernes et performants, tout en offrant des stratégies marketing efficaces pour maximiser la visibilité de nos clients.</p>
      </div>
    </div>
  </section>
</template>

<script>
import { images } from '../assets/images'

export default {
  name: 'AboutUs',
  data() {
    return {
      teamImage: images.teamImage
    }
  }
}
</script>

<style scoped>
.about-section {
  padding: 5rem 2rem;
  background-color: #f9f9f9;
}

.about-content {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}

.about-image img {
  width: 100%;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.about-text h2 {
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
  color: #333;
}

.about-text p {
  margin-bottom: 1rem;
  line-height: 1.6;
  color: #666;
}

@media (max-width: 768px) {
  .about-section {
    padding: 3rem 1rem;
  }

  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .about-text h2 {
    font-size: 2rem;
    text-align: center;
  }

  .about-text p {
    text-align: center;
  }
}
</style> 