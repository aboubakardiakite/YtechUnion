<template>
  <div class="service-card">
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <ul class="service-steps">
      <li v-for="(step, index) in steps" :key="index">{{ step }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ServiceCard',
  props: {
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    steps: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style scoped>
.service-card {
  background: #1a1a1a;
  color: white;
  padding: 2rem;
  border-radius: 8px;
  text-align: center;
  transition: transform 0.3s ease;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  height: 100%;
  display: flex;
  flex-direction: column;
}

.service-card:hover {
  transform: translateY(-5px);
}

.service-card h3 {
  margin-bottom: 1rem;
  color: #FFD700;
  font-size: 1.5rem;
}

.service-card p {
  color: #f0f0f0;
  margin-bottom: 1rem;
  font-size: 1rem;
  line-height: 1.4;
}

.service-steps {
  text-align: left;
  list-style-type: none;
  padding: 0;
  margin-top: 1rem;
  flex-grow: 1;
}

.service-steps li {
  margin-bottom: 0.7rem;
  padding-left: 1.5rem;
  position: relative;
  color: #e0e0e0;
  font-size: 0.9rem;
  line-height: 1.3;
}

.service-steps li:before {
  content: "✓";
  color: #FFD700;
  position: absolute;
  left: 0;
}

@media (max-width: 768px) {
  .service-card {
    padding: 1.5rem;
  }

  .service-card h3 {
    font-size: 1.3rem;
  }

  .service-card p {
    font-size: 0.95rem;
  }

  .service-steps li {
    margin-bottom: 0.6rem;
    font-size: 0.85rem;
  }
}
</style> 