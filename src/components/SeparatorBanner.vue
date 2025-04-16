<template>
  <section class="separator-banner">
    <div class="banner-content">
      <h2>CCONSTRUIRE UN SITE WEB SOLIDE, C’EST ASSURER LA RÉUSSITE DE VOTRE PROJET.</h2>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SeparatorBanner'
}
</script>

<style scoped>
.separator-banner {
  width: 100%;
  background: #1a1a1a; /* Couleur violette comme dans l'image */
  padding: 4rem 2rem;
  position: relative;
  overflow: hidden;
}

.banner-content {
  max-width: 1400px;
  margin: 0 auto;
  text-align: center;
}

h2 {
  color: white;
  font-size: 2.8rem;
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
  font-family: 'Space Grotesk', sans-serif; /* Police similaire à celle de l'image */
  line-height: 1.2;
}

/* Animation subtile au survol */
.separator-banner:hover h2 {
  transform: scale(1.02);
  transition: transform 0.3s ease;
}

@media (max-width: 1024px) {
  h2 {
    font-size: 2.2rem;
  }
}

@media (max-width: 768px) {
  .separator-banner {
    padding: 3rem 1.5rem;
  }

  h2 {
    font-size: 1.8rem;
    letter-spacing: 1px;
  }
}
</style> 