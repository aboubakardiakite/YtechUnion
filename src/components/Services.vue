<template>
  <section id="services" class="services-section">
    <h2>Nos services</h2>
    <div class="services-grid">
      <ServiceCard
        v-for="service in services"
        :key="service.id"
        :icon="service.icon"
        :title="service.title"
        :description="service.description"
      />
    </div>
  </section>
</template>

<script>
import ServiceCard from './ServiceCard.vue'
import { images } from '../assets/images'

export default {
  name: 'Services',
  components: {
    ServiceCard
  },
  data() {
    return {
      services: [
        {
          id: 1,
          icon: images.webDevIcon,
          title: 'Développement web',
          description: 'Nous créons des sites web modernes et performants adaptés à vos besoins.'
        },
        {
          id: 2,
          icon: images.seoIcon,
          title: 'SEO et Marketing',
          description: 'Optimisez votre visibilité et attirez plus de clients grâce au SEO'
        },
        {
          id: 3,
          icon: images.brandingIcon,
          title: 'Branding',
          description: "Développez l'identité de votre marque avec un design et une stratégie clairs"
        }
      ]
    }
  }
}
</script>

<style scoped>
.services-section {
  padding: 5rem 2rem;
}

h2 {
  text-align: center;
  margin-bottom: 3rem;
  font-size: 2.5rem;
  color: #333;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

@media (max-width: 768px) {
  .services-section {
    padding: 3rem 1rem;
  }

  h2 {
    font-size: 2rem;
  }

  .services-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
}
</style> 