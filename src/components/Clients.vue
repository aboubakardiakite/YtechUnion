<template>
  <section id="clients" class="clients-section">
    <h2>Ils nous font confiance</h2>
    <div class="clients-logos">
      <a v-for="client in clients" 
         :key="client.id" 
         :href="client.site" 
         target="_blank" 
         class="client-logo">
        <img :src="client.logo" :alt="client.nom">
        <div class="client-hover">
          <span>{{ client.nom }}</span>
        </div>
      </a>
    </div>
  </section>
</template>

<script>
import LearnCyberLogo from '../assets/images/LearnCyber.png'
import PropulseLogo from '../assets/images/propulse.png'
import NarcisseLogo from '../assets/images/narcisse.png'

export default {
  name: 'Clients',
  data() {
    return {
      clients: [
        {
          id: 1,
          nom: 'Learn Cyber',
          logo: LearnCyberLogo,
          site: 'https://learncyber.vercel.app/'
        },
        {
          id: 2,
          nom: 'Propulse',
          logo: PropulseLogo,
          site: 'https://propulse-site.vercel.app/'
        },
        {
          id: 3,
          nom: 'Narcisse',
          logo: NarcisseLogo,
          site: 'https://narcisse.vercel.app/'
        }
      ]
    }
  }
}
</script>

<style scoped>
.clients-section {
  padding: 6rem 2rem;
  background-color: #f9f9f9;
}

h2 {
  text-align: center;
  margin-bottom: 4rem;
  font-size: 2.8rem;
  color: #333;
}

.clients-logos {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 4rem;
  max-width: 1200px;
  margin: 0 auto;
  flex-wrap: wrap;
}

.client-logo {
  width: 200px;
  height: 200px;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  background-color: white;
  box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  padding: 2rem;
  border: 2px solid transparent;
  position: relative;
}

.client-hover {
  position: absolute;
  top: -40px;
  left: 50%;
  transform: translateX(-50%) translateY(10px);
  background-color: #333;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  font-size: 0.9rem;
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
  white-space: nowrap;
}

.client-hover::after {
  content: '';
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translateX(-50%);
  border-width: 5px;
  border-style: solid;
  border-color: #333 transparent transparent transparent;
}

.client-logo:hover .client-hover {
  opacity: 1;
  visibility: visible;
  transform: translateX(-50%) translateY(0);
}

.client-logo:hover {
  transform: scale(1.1);
  border-color: #FF6B00;
  box-shadow: 0 6px 25px rgba(0,0,0,0.15);
}

.client-logo img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
  border-radius: 50%;
}

@media (max-width: 768px) {
  .clients-section {
    padding: 4rem 1rem;
  }

  h2 {
    font-size: 2.2rem;
    margin-bottom: 3rem;
  }

  .clients-logos {
    gap: 2rem;
  }

  .client-logo {
    width: 150px;
    height: 150px;
    padding: 1.5rem;
  }

  .client-hover {
    font-size: 0.8rem;
    top: -35px;
    padding: 0.4rem 0.8rem;
  }
}
</style> 