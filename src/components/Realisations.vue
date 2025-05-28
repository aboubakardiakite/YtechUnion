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

          <!-- Section des avis clients -->
          <div class="avis-section" v-if="projet.avis && projet.avis.length > 0">
            <h4>Avis de nos clients</h4>
            <div class="avis-container">
              <div v-for="(avis, index) in projet.avis" :key="index" class="avis-card">
                <div class="avis-header">
                  <span class="avis-client">{{ avis.client }}</span>
                </div>
                <p class="avis-commentaire">{{ avis.commentaire }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import LearnCyberLanding from '../assets/images/leardingPageLearCber.png'
import PropulseLanding from '../assets/images/leardingPagePropulse.png'
import NarcisseLanding from '../assets/images/leardingPageNarcisse.png'

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
          lien: 'https://learncyber.vercel.app/',
          avis: [
            {
              client: 'SCANDELLA Anthony',
              commentaire: 'Vu la qualité du travail fourni par Ytechunion, nous ne pouvons que vous remercier !\n' +
                'Un grand merci à vous pour votre écoute et la collaboration tout au long de notre refonte de site web. \n' +
                'Vous avez su être force de proposition et innovant sur un sujet que nous ne maîtrisions pas ou peu. \n' +
                'Un grand merci !',
              note: 5
            }
          ]
        },
        {
          id: 2,
          titre: 'Propulse',
          description: 'Plateforme spécialisée en e-réputation et communication pour les sportifs',
          keyPoints: [
            'Design moderne et impactant',
            'Navigation fluide',
            'Présentation claire des services'
          ],
          image: PropulseLanding,
          lien: 'https://propulse-site.vercel.app/',
          avis: [
            {
              client: 'TOURÉ Aminata',
              commentaire: 'On a vraiment apprécié travailler avec toi et ton équipe sur la création de notre site internet. Tu as été à l’écoute du début à la fin, en prenant en compte chacun de nos retours avec attention et réactivité. Le résultat est fidèle à ce qu’on imaginait. Merci pour ton accompagnement et ton professionnalisme.',
              note: 5
            }
          ]
        },
        {
          id: 3,
          titre: 'Narcisse',
          description: 'Une plateforme spécialisée dans la valorisation de l’image des marques à travers des productions visuelles.',
          keyPoints: [
            'Design moderne et impactant',
            'Navigation fluide',
            'Présentation claire des services'
          ],
          image: NarcisseLanding,
          lien: 'https://narcisse.vercel.app/',
          avis: [
            {
              client: 'LOBBESTAEL Alexandre',
              commentaire: 'Un grand merci à YTechUnion pour leur travail sur notre site web, ils ont su livrer une première version rapidement, avec une très bonne compréhension de nos attentes. Les échanges ont été simples et efficaces, et leur autonomie a vraiment facilité la collaboration.',
              note: 5
            }
          ]
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

/* Styles pour la section des avis */
.avis-section {
  margin-top: 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding-top: 1.5rem;
}

.avis-section h4 {
  color: #FFD700;
  font-size: 1.2rem;
  margin-bottom: 1rem;
  text-align: center;
}

.avis-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.avis-card {
  background-color: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
  padding: 1rem;
  transition: transform 0.2s ease;
}

.avis-card:hover {
  transform: translateY(-2px);
  background-color: rgba(255, 255, 255, 0.08);
}

.avis-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}

.avis-client {
  font-weight: bold;
  color: #e0e0e0;
}


.avis-commentaire {
  font-size: 0.9rem;
  line-height: 1.4;
  color: #d0d0d0;
  font-style: italic;
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

  .avis-section h4 {
    font-size: 1.1rem;
  }

  .avis-card {
    padding: 0.8rem;
  }

  .avis-client {
    font-size: 0.9rem;
  }

  .avis-commentaire {
    font-size: 0.8rem;
  }
}
</style> 
