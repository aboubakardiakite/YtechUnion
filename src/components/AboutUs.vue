<template>
  <section id="qui-sommes-nous" class="about-section">
    <div class="about-content">
      <div class="about-text">
        <h2>YTECH TEAM</h2>
        <p class="main-description">
          Nous sommes une équipe dynamique de professionnels passionnés par le développement web, 
          l'innovation et le marketing digital. Notre mission est de créer des solutions web 
          performantes et innovantes pour nos clients.
        </p>
      </div>

      <div class="team-carousel">
        <button class="carousel-btn prev" @click="prevMember">&lt;</button>
        
        <div class="carousel-container">
          <div class="carousel-track" :style="carouselStyle">
            <div v-for="member in teamMembers" 
                 :key="member.id" 
                 class="team-member">
              <div class="member-image">
                <img :src="member.image" :alt="member.name">
              </div>
              <div class="member-info">
                <h3>{{ member.name }}</h3>
                <p class="role">{{ member.role }}</p>
                <p class="description">{{ member.description }}</p>
                <div class="member-skills">
                  <span v-for="skill in member.skills" 
                        :key="skill" 
                        class="skill-tag">
                    {{ skill }}
                  </span>
                </div>
                <div class="social-links">
                  <a v-if="member.linkedin" :href="member.linkedin" target="_blank">
                    <i class="fab fa-linkedin"></i>
                  </a>
                  <a v-if="member.github" :href="member.github" target="_blank">
                    <i class="fab fa-github"></i>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>

        <button class="carousel-btn next" @click="nextMember">&gt;</button>
      </div>

      <div class="carousel-indicators">
        <button v-for="(member, index) in teamMembers" 
                :key="index"
                :class="['indicator', { active: currentIndex === index }]"
                @click="goToMember(index)">
        </button>
      </div>
    </div>
  </section>
</template>

<script>
import AxelImage from '../assets/images/axel.png' // Ajustez le chemin selon votre structure
import AntoineImage from '../assets/images/antoine.png'
import ThomasImage from '../assets/images/thomas.png'
import AboubakarImage from '../assets/images/aboubakar.jpg'

export default {
  name: 'AboutUs',
  data() {
    return {
      currentIndex: 0,
      teamMembers: [
        {
          id: 1,
          name: 'Thomas Cornu',
          role: 'Chef de projet',
          description: 'Passionné par le développement web et la création d\'expériences utilisateur innovantes.',
          skills: ['Jira','UI/UX Design'],
          image: ThomasImage,
          linkedin:'https://www.linkedin.com/in/thomas-cornu-/',
          github: '#'
        },
    
        {
          id: 2,
          name: 'aboubakar Diakite',
          role: 'Développeur Full Stack',
          description: 'Passionné par le développement et la création d\'applications web innovantes.',
          skills: ['Vue.js', 'JavaScript', 'UI/UX Design'],
          image: AboubakarImage,
          linkedin: 'www.linkedin.com/in/abou-diakite',
          github: '#'
        },
        {
          id: 3,
          name: 'Axel Carry',
          role: 'Dévops',
          description: 'Spécialiste en sécurité des applications et protection des données.',
          skills: ['Sécurité Web', 'Pentesting', 'Audit', 'DevSecOps'],
          image: AxelImage,
          linkedin: 'https://www.linkedin.com/in/antoine-raimand/',
          github: '#'
        },
        {
          id: 4,
          name: 'Antoine Raimand',
          role: 'Développeur Full Stack',
          description: 'Passionné par le développement et la création d\'applications web innovantes.',
          skills: ['React.js', 'JavaScript', 'UI/UX Design', 'Web Development'],
          image: AntoineImage,
          linkedin: 'https://www.linkedin.com/in/axel-carry-a01b68213/',
          github: '#'
        }
      ]
    }
  },
  computed: {
    carouselStyle() {
      return {
        transform: `translateX(-${this.currentIndex * 100}%)`
      }
    }
  },
  methods: {
    nextMember() {
      this.currentIndex = (this.currentIndex + 1) % this.teamMembers.length
    },
    prevMember() {
      this.currentIndex = this.currentIndex === 0 
        ? this.teamMembers.length - 1 
        : this.currentIndex - 1
    },
    goToMember(index) {
      this.currentIndex = index
    }
  }
}
</script>

<style scoped>
.about-section {
  padding: 8rem 2rem 6rem;
  background-color: #1a1a1a;
  color: white;
  position: relative;
  margin-top: 100px; /* Espace pour l'effet de séparation */
}

/* Effet de séparation */
.about-section::before {
  content: '';
  position: absolute;
  top: -100px;
  left: 0;
  right: 0;
  height: 100px;
  background: #1a1a1a;
  clip-path: polygon(0 0, 100% 100%, 100% 100%, 0% 100%);
}

/* Ligne dorée de séparation */
.about-section::after {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 4px;
  background: #FFD700;
  border-radius: 2px;
}

.about-content {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
  position: relative;
}

h2 {
  color: #FFD700;
  font-size: 2.8rem;
  margin-bottom: 2rem;
}

.main-description {
  color: #f0f0f0;
  font-size: 1.2rem;
  line-height: 1.6;
  margin-bottom: 4rem;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

.team-carousel {
  position: relative;
  display: flex;
  align-items: center;
  margin-bottom: 2rem;
}

.carousel-container {
  width: 100%;
  overflow: hidden;
}

.carousel-track {
  display: flex;
  transition: transform 0.5s ease;
}

.team-member {
  min-width: 100%;
  display: flex;
  gap: 3rem;
  padding: 2rem;
}

.member-image {
  flex: 0 0 300px;
}

.member-image img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 8px;
  border: 2px solid #FFD700;
}

.member-info {
  flex: 1;
  text-align: left;
}

.member-info h3 {
  color: #FFD700;
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.role {
  color: #f0f0f0;
  font-size: 1.2rem;
  margin-bottom: 1rem;
}

.description {
  color: #e0e0e0;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.member-skills {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.skill-tag {
  background: #333;
  color: #FFD700;
  padding: 0.4rem 1rem;
  border-radius: 20px;
  font-size: 0.9rem;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-links a {
  color: #FFD700;
  font-size: 1.5rem;
  transition: transform 0.3s ease;
}

.social-links a:hover {
  transform: translateY(-3px);
}

.carousel-btn {
  background: none;
  border: none;
  color: #FFD700;
  font-size: 2rem;
  cursor: pointer;
  padding: 1rem;
  transition: transform 0.3s ease;
}

.carousel-btn:hover {
  transform: scale(1.2);
}

.carousel-indicators {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  margin-top: 2rem;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #333;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.indicator.active {
  background: #FFD700;
}

@media (max-width: 968px) {
  .team-member {
    flex-direction: column;
    gap: 2rem;
  }

  .member-image {
    flex: 0 0 auto;
  }

  .member-info {
    text-align: center;
  }

  .member-skills {
    justify-content: center;
  }

  .social-links {
    justify-content: center;
  }
}

@media (max-width: 768px) {
  .about-section {
    margin-top: 60px; /* Ajustement pour mobile */
  }

  .about-section::before {
    top: -60px;
    height: 60px;
  }

  .about-section {
    padding: 4rem 1rem;
  }

  h2 {
    font-size: 2.2rem;
  }

  .main-description {
    font-size: 1.1rem;
    margin-bottom: 3rem;
  }

  .member-image {
    width: 250px;
    margin: 0 auto;
  }

  .member-info h3 {
    font-size: 1.8rem;
  }
}
</style> 