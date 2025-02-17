<template>
  <div class="service-card">
    <img :src="icon" :alt="title">
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: 'ServiceCard',
  props: {
    icon: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.service-card {
  background: #f5f5f5;
  padding: 2rem;
  border-radius: 8px;
  text-align: center;
  transition: transform 0.3s ease;
}

.service-card:hover {
  transform: translateY(-5px);
}

.service-card img {
  width: 64px;
  height: 64px;
  margin-bottom: 1rem;
}

.service-card h3 {
  margin-bottom: 1rem;
}

@media (max-width: 768px) {
  .service-card {
    padding: 1.5rem;
  }

  .service-card h3 {
    font-size: 1.2rem;
  }

  .service-card img {
    width: 48px;
    height: 48px;
  }
}
</style> 