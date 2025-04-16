<template>
  <section id="services" class="services-section">
    <h2>Nos services</h2>
    <div class="services-grid">
      <ServiceCard
        v-for="service in services"
        :key="service.id"
        :title="service.title"
        :description="service.description"
        :steps="service.steps"
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
          title: 'Création de Site Web de A à Z',
          description: 'Donnez vie à votre présence en ligne avec notre solution complète et personnalisée. Notre approche méthodique garantit un site web qui répond parfaitement à vos objectifs.',
          steps: [
            'Consultation initiale approfondie pour comprendre vos besoins et objectifs',
            'Analyse stratégique et élaboration du cahier des charges détaillé',
            'Sessions de co-création pour valider la direction artistique',
            'Design moderne et responsive adapté à votre image',
            'Développement technique optimisé pour la performance',
            'Tests approfondis et contrôle qualité rigoureux',
            'Déploiement et accompagnement personnalisé',
            'Options : SEO, hébergement, formation utilisateur'
          ]
        },
        {
          id: 2,
          title: 'Accompagnement Digital Global',
          description: 'Une stratégie digitale sur mesure pour propulser votre entreprise vers le succès. Idéal pour les entrepreneurs et organisations en pleine croissance.',
          steps: [
            'Audit complet de votre présence digitale',
            'Élaboration d\'une stratégie digitale personnalisée',
            'Développement ou optimisation de votre site web',
            'Mise en place d\'outils digitaux performants',
            'Analyse et optimisation des performances',
            'Accompagnement régulier et ajustements stratégiques',
            'Formation et transfert de compétences',
            'Support continu pour votre évolution digitale'
          ]
        },
        {
          id: 3,
          title: 'Maintenance & Support Technique',
          description: 'Gardez votre site web performant et sécurisé avec notre service de maintenance professionnel. Une tranquillité d\'esprit garantie pour votre présence en ligne.',
          steps: [
            'Audit technique approfondi de votre plateforme',
            'Optimisation continue des performances',
            'Mises à jour de sécurité proactives',
            'Sauvegardes automatiques sécurisées',
            'Monitoring 24/7 de la disponibilité',
            'Support technique réactif et professionnel',
            'Maintenance préventive régulière',
            'Interventions d\'urgence garanties'
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
.services-section {
  padding: 6rem 2rem;
  background-color: #f9f9f9;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

h2 {
  text-align: center;
  margin-bottom: 3rem;
  font-size: 2.8rem;
  color: #333;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  max-width: 1800px;
  margin: 0 auto;
  align-items: stretch;
}

@media (max-width: 1400px) {
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 900px) {
  .services-section {
    padding: 4rem 1.5rem;
  }

  h2 {
    font-size: 2.2rem;
    margin-bottom: 2rem;
  }

  .services-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
}

@media (max-width: 480px) {
  .services-section {
    padding: 3rem 1rem;
  }

  h2 {
    font-size: 2rem;
  }
}
</style> 