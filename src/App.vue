<template>
  <div id="app">
    <Header />
    <main class="main-content">
      <Hero />
      <AboutUs />
      <Services />
      <Clients />
      <Contact />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import AboutUs from './components/AboutUs.vue'
import Services from './components/Services.vue'
import Clients from './components/Clients.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    AboutUs,
    Services,
    Clients,
    Contact,
    Footer
  }
}
</script>

<style>
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.main-content {
  padding-top: 80px; /* Hauteur du header */
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
  scroll-padding-top: 80px; /* Pour le défilement ancré */
}
</style>
