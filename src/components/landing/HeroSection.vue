<script setup lang="ts">
import IconSearch from '../icons/IconSearch.vue'
</script>
<template>
  <div class="hero-section">
    <div class="carousel">
      <div class="carousel-inner" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
        <div class="carousel-item" v-for="(image, index) in images" :key="index">
          <img :src="image" class="w-full h-screen object-cover filter-dark overlay-red" />
        </div>
      </div>
      <button class="carousel-control prev" @click="prevSlide">‹</button>
      <button class="carousel-control next" @click="nextSlide">›</button>
    </div>
    <div class="overlay">
      <h1 class="text-white text-4xl font-bold mb-4">Bienvenido a Nuestro Sitio</h1>
      <h1 class="text-white text-xl mb-4">Fields, teams and utilities in just few Clicks</h1>
      <div class="flex p-1 rounded-4xl items-center text-sm bg-gray-300 ">
        <IconSearch class="w-4 h-4 text-gray-500 " />
        <input type="text" placeholder="Buscar..." class="p-2 rounded w-64 outline-0 "/>
        <span class="text-white ">|</span>
        <select name="" id="" class="p-2 rounded ml-2 w-52 justify-end ">
          <option value="1">Futbol</option>
          <option value="2">Basket</option>
          <option value="3">Volley</option>
        </select>
        <IconSearch class="w-10 h-10 text-gray-500 bg-primary rounded-4xl p-2 m-1" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      currentIndex: 0,
      images: [
        'public/images/Stadium1.jpg',
        'public/images/Stadium2.jpg',
        'public/images/Stadium3.jpg',
      ],
    }
  },
  methods: {
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length
    },
    prevSlide() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length
    },
  },
  mounted() {
    setInterval(this.nextSlide, 5000)
  },
}
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

.overlay-red::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 50%;
  background: linear-gradient(to top, rgba(255, 0, 0, 0.5), transparent);
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
