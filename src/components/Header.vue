<template>
  <header class="header">
    <div class="logo">
      <h1>YTECH UNION</h1>
    </div>
    <button class="nav-toggle" @click="toggleMenu" aria-label="Toggle menu">
      <i :class="['fas', isMenuOpen ? 'fa-times' : 'fa-bars']"></i>
    </button>
    <nav :class="['nav', { active: isMenuOpen }]">
      <ul>
        <li><a :class="{ active: activeSection === 'accueil' }" href="#accueil" @click="closeMenu">Accueil</a></li>
        <li><a :class="{ active: activeSection === 'qui-sommes-nous' }" href="#qui-sommes-nous" @click="closeMenu">Qui sommes nous?</a></li>
        <li><a :class="{ active: activeSection === 'services' }" href="#services" @click="closeMenu">Nos services</a></li>
        <li><a :class="{ active: activeSection === 'clients' }" href="#clients" @click="closeMenu">Nos clients</a></li>
        <li><a :class="{ active: activeSection === 'contact' }" href="#contact" @click="closeMenu">Contact</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      activeSection: 'accueil',
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
      document.body.style.overflow = this.isMenuOpen ? 'hidden' : ''
    },
    closeMenu() {
      this.isMenuOpen = false
      document.body.style.overflow = ''
    }
  },
  mounted() {
    const sections = ['accueil', 'qui-sommes-nous', 'services', 'clients', 'contact']
    
    const observerOptions = {
      root: null,
      rootMargin: '-50% 0px',
      threshold: 0
    }

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          this.activeSection = entry.target.id
        }
      })
    }, observerOptions)

    sections.forEach(section => {
      const element = document.getElementById(section)
      if (element) observer.observe(element)
    })
  }
}
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: #1a1a1a;
  color: #fff;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.logo h1 {
  color: #FFD700;
}

.nav-toggle {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 1.5rem;
  cursor: pointer;
  padding: 0.5rem;
  transition: color 0.3s ease;
}

.nav-toggle:hover {
  color: #FFD700;
}

.nav ul {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav a {
  color: white;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  position: relative;
}

.nav a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #FFD700;
  transition: width 0.3s ease;
}

.nav a.active {
  color: #FFD700;
}

.nav a.active::after {
  width: 100%;
}

.nav a:hover {
  color: #FFD700;
}

.nav a:hover::after {
  width: 100%;
}

@media (max-width: 768px) {
  .header {
    padding: 1rem;
  }

  .nav-toggle {
    display: block;
    order: 3;
  }

  .logo {
    order: 1;
  }

  .nav {
    order: 2;
    width: 100%;
  }

  .nav ul {
    display: none;
    position: fixed;
    top: 80px;
    left: 0;
    right: 0;
    flex-direction: column;
    background-color: #1a1a1a;
    padding: 1rem;
    gap: 1rem;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  }

  .nav.active ul {
    display: flex;
  }

  .logo h1 {
    font-size: 1.2rem;
  }

  .nav a::after {
    display: none;
  }

  .nav a {
    display: block;
    padding: 0.8rem;
    text-align: center;
  }

  .nav a.active {
    background-color: rgba(255, 215, 0, 0.1);
    border-radius: 4px;
  }
}
</style> 