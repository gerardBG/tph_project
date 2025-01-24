<template>
  <div class="banner">
    <div class="banner-content">
      <h1 v-if="title.length > 0" class="banner-title">{{ title }}</h1>
      <p v-if="description.length > 0" class="banner-description">{{ description }}</p>
      <button v-if="ctaHandler.length > 0" class="banner-button" @click="ctaHandler">
        {{ buttonText }}
      </button>
    </div>
  </div>
</template>
  
  <script>
// Definir las props para personalizar el banner
export default {
  props: {
    title: {
      type: String,
      default: "",
    },
    description: {
      type: String,
      default: "",
    },
    buttonText: {
      type: String,
      default: "",
    },
    ctaHandler: {
      type: Function,
      default: () => {
        alert("¡Acción ejecutada!");
      },
    },
  },
};
</script>
  
  <style scoped>
.banner {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  color: #fff;
  text-align: center;
  border-radius: 8px;
  background-image: url('/src/assets/banner.webp');
  background-repeat: no-repeat;
  width: 100%;
}

.banner-content {
  max-width: 600px;
}

.banner-title {
  font-size: 2rem;
  margin-bottom: 10px;
}

.banner-description {
  font-size: 1rem;
  margin-bottom: 20px;
}

.banner-button {
  background-color: #fff;
  color: #4c9aff;
  border: none;
  border-radius: 4px;
  padding: 10px 20px;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.banner-button:hover {
  background-color: #4c9aff;
  color: #fff;
}
</style>
  