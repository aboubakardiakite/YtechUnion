<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-section">
        <h3>YTECH UNION</h3>
        <p>Créons ensemble votre présence numérique avec des solutions web innovantes et performantes.</p>
      </div>

      <div class="footer-section">
        <h3>Liens Rapides</h3>
        <ul>
          <li><a href="#accueil">Accueil</a></li>
          <li><a href="#qui-sommes-nous">Qui sommes nous?</a></li>
          <li><a href="#services">Nos services</a></li>
          <li><a href="#clients">Nos clients</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>

      <div class="footer-section">
        <h3>Nos Services</h3>
        <ul>
          <li>Création de Site Web de A à Z</li>
          <li>Accompagnement Digital Global</li>
          <li>Maintenance & Support Technique</li>
        </ul>
      </div>

      <div class="footer-section">
        <h3>Contact</h3>
        <ul class="contact-info">
          <li>
            <i class="fas fa-envelope"></i>
            contact@ytechunion.com
          </li>
          <li>
            <i class="fas fa-phone"></i>
            +33 1 23 45 67 89
          </li>
          <li>
            <i class="fas fa-map-marker-alt"></i>
            Lille, France
          </li>
        </ul>
      </div>
    </div>

    <div class="footer-bottom">
      <div class="social-links">
        <a href="#" target="_blank"><i class="fab fa-linkedin"></i></a>
        <a href="#" target="_blank"><i class="fab fa-twitter"></i></a>
        <a href="#" target="_blank"><i class="fab fa-facebook"></i></a>
        <a href="#" target="_blank"><i class="fab fa-instagram"></i></a>
      </div>
      <p>&copy; {{ currentYear }} YTECH UNION. Tous droits réservés.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  computed: {
    currentYear() {
      return new Date().getFullYear()
    }
  }
}
</script>

<style scoped>
.footer {
  background-color: #1a1a1a;
  color: #fff;
  padding: 4rem 2rem 2rem;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.footer-section h3 {
  color: #FFD700;
  margin-bottom: 1.5rem;
  font-size: 1.2rem;
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.footer-section ul li {
  margin-bottom: 0.8rem;
}

.footer-section a {
  color: #fff;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-section a:hover {
  color: #FFD700;
}

.contact-info li {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.footer-bottom {
  max-width: 1200px;
  margin: 0 auto;
  padding-top: 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  text-align: center;
}

.social-links {
  margin-bottom: 1.5rem;
}

.social-links a {
  color: #fff;
  font-size: 1.5rem;
  margin: 0 1rem;
  transition: color 0.3s ease;
}

.social-links a:hover {
  color: #FFD700;
}

.footer-bottom p {
  color: #888;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .footer {
    padding: 3rem 1rem 1rem;
  }

  .footer-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }

  .footer-section {
    padding: 0 1rem;
  }

  .contact-info li {
    justify-content: center;
  }

  .social-links {
    display: flex;
    justify-content: center;
    gap: 1.5rem;
  }

  .social-links a {
    margin: 0;
  }
}

@media (max-width: 480px) {
  .footer-section h3 {
    font-size: 1.1rem;
  }
}
</style> 