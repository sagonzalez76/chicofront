<template>
  <div class="hero-section">
    <div class="carousel">
      <div class="carousel-inner" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
        <div class="carousel-item" v-for="(image, index) in images" :key="index">
          <img :src="image" class="w-full h-screen object-cover filter-dark" />
        </div>
      </div>
      <button class="carousel-control prev" @click="prevSlide">‹</button>
      <button class="carousel-control next" @click="nextSlide">›</button>
    </div>
    <div class="overlay">
      <h1 class="text-white text-4xl font-bold mb-4">Bienvenido a Nuestro Sitio</h1>
      <input type="text" placeholder="Buscar..." class="p-2 rounded" />
    </div>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      currentIndex: 0,
      images: [
        'https://assets.goal.com/images/v3/blt0bea61fc82528a87/dbbd6d07d4b7a8ed98fa0e0c37b3516c9aef605b.jpg',
        'https://www.directvsports.com/__export/1707399853068/sites/dsports/img/2024/02/08/untitled_design_-93-.png_1937756784.png',
        'https://i.imgur.com/geKvCH9.jpg'
      ]
    };
  },
  methods: {
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevSlide() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    }
  },
  mounted() {
    setInterval(this.nextSlide, 5000);
  }
};
</script>

<style scoped>
.hero-section {
  width: 100%;
  overflow: hidden;
  position: relative;
}

.carousel {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.carousel-inner {
  display: flex;
  transition: transform 2s ease-in-out;
}

.carousel-item {
  min-width: 100%;
  position: relative;
}

.carousel-item img {
  width: 100%;
  height: 100vh;
  object-fit: cover;
}

.filter-dark {
  filter: brightness(50%);
}

.overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  z-index: 10;
}

.carousel-control {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
  z-index: 10;
}

.carousel-control.prev {
  left: 10px;
}

.carousel-control.next {
  right: 10px;
}
</style>