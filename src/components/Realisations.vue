<template>
  <section id="realisations" class="realisations-section">
    <h2>Nos Réalisations</h2>
    <div class="realisations-grid">
      <div v-for="projet in projets" :key="projet.id" class="realisation-card">
        <div class="realisation-image">
          <img :src="projet.image" :alt="projet.titre">
        </div>
        <div class="realisation-content">
          <h3>{{ projet.titre }}</h3>
          <p class="description">{{ projet.description }}</p>
          <div class="key-points">
            <ul>
              <li v-for="(point, index) in projet.keyPoints" :key="index">
                {{ point }}
              </li>
            </ul>
          </div>
          <a :href="projet.lien" target="_blank" class="visit-btn">
            Visiter le site
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import LearnCyberLanding from '../assets/images/leardingPageLearCber.png'
import PropulseLanding from '../assets/images/leardingPagePropulse.png'

export default {
  name: 'Realisations',
  data() {
    return {
      projets: [
        {
          id: 1,
          titre: 'Learn Cyber',
          description: 'Plateforme éducative dédiée à la cybersécurité, offrant des cours et des ressources pédagogiques de qualité.',
          keyPoints: [
            'Interface intuitive et moderne',
            'Système de gestion de cours',
            'Contenu sécurisé et structuré'
          ],
          image: LearnCyberLanding,
          lien: 'https://learncyber.vercel.app/'
        },
        {
          id: 2,
          titre: 'Propulse',
          description: 'Site web professionnel mettant en avant les services et l\'expertise de Propulse dans le domaine du développement web.',
          keyPoints: [
            'Design moderne et impactant',
            'Navigation fluide',
            'Présentation claire des services'
          ],
          image: PropulseLanding,
          lien: 'https://propulse-site.vercel.app/'
        }
      ]
    }
  }
}
</script>

<style scoped>
.realisations-section {
  padding: 6rem 2rem;
  background-color: #f9f9f9;
}

h2 {
  text-align: center;
  margin-bottom: 3rem;
  font-size: 2.8rem;
  color: #333;
}

.realisations-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  max-width: 1400px;
  margin: 0 auto;
}

.realisation-card {
  background: #1a1a1a;
  color: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  transition: transform 0.3s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.realisation-card:hover {
  transform: translateY(-5px);
}

.realisation-image {
  width: 100%;
  height: 250px;
  overflow: hidden;
  background-color: #1a1a1a;
}

.realisation-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.realisation-card:hover .realisation-image img {
  transform: scale(1.05);
}

.realisation-content {
  padding: 2rem;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.realisation-content h3 {
  color: #FFD700;
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.description {
  color: #f0f0f0;
  margin-bottom: 1rem;
  line-height: 1.4;
  font-size: 1rem;
}

.key-points {
  margin-bottom: 1.5rem;
}

.key-points ul {
  list-style: none;
  padding: 0;
  text-align: left;
}

.key-points li {
  color: #e0e0e0;
  font-size: 0.9rem;
  margin-bottom: 0.7rem;
  padding-left: 1.5rem;
  position: relative;
  line-height: 1.3;
}

.key-points li:before {
  content: "✓";
  color: #FFD700;
  position: absolute;
  left: 0;
}

.visit-btn {
  display: inline-block;
  background: #FFD700;
  color: #1a1a1a;
  padding: 0.8rem 2rem;
  border-radius: 25px;
  text-decoration: none;
  transition: all 0.3s ease;
  font-weight: bold;
  text-align: center;
  margin-top: auto;
}

.visit-btn:hover {
  background: #ffd900;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .realisations-section {
    padding: 4rem 1rem;
  }

  h2 {
    font-size: 2.2rem;
    margin-bottom: 2rem;
  }

  .realisation-content {
    padding: 1.5rem;
  }

  .realisation-content h3 {
    font-size: 1.3rem;
  }

  .realisation-image {
    height: 200px;
  }
}
</style> 