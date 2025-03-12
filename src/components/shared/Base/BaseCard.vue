<script lang="ts" setup>
import { ref } from 'vue';

const props = defineProps({
  images: {
    type: Array as () => string[],
    required: true,
    default: () => []
  },
  price: {
    type: Number,
    required: true,
    default: 4100
  },
  currency: {
    type: String,
    default: 'LKR',
  },
  title: {
    type: String,
    required: true,
    default: ''
  },
  city: {
    type: String,
    required: true,
    default: ''
  },
  time: {
    type: Number,
    required: true,
    default: 1
  },
  players: {
    type: Number,
    required: true,
    default: 1
  },
});

const currentImageIndex = ref(0);

const nextImage = () => {
  currentImageIndex.value = (currentImageIndex.value + 1) % props.images.length;
};

const prevImage = () => {
  currentImageIndex.value = (currentImageIndex.value - 1 + props.images.length) % props.images.length;
};
</script>

<template>
  <div class="border rounded-lg shadow max-w-sm bg-white relative">
    <div class="relative group">
      <div class="absolute m-2 justify-end">
        <span class="bg-green-500 text-white text-sm px-3 py-1 rounded-full">For Rent</span>
      </div>
      <img :src="props.images[currentImageIndex]" alt="Property Image" class="w-full h-full object-cover rounded-lg" />
      
      <!-- Botones de navegación -->
      <button 
        @click="prevImage"
        class="absolute left-2 top-1/2 transform -translate-y-1/2 bg-white text-black w-8 h-8 flex items-center justify-center rounded-full shadow opacity-0 group-hover:opacity-100 transition-opacity duration-300"
      >
        ‹
      </button>

      <button 
        @click="nextImage"
        class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-white text-black w-8 h-8 flex items-center justify-center rounded-full shadow opacity-0 group-hover:opacity-100 transition-opacity duration-300"
      >
        ›
      </button>
    </div>
    <div class="mt-4 p-2">
      <div class="flex text-red-500 text-lg font-semibold">
        {{ props.price }} {{ props.currency }} <span class="flex text-black text-md ml-2">/Month</span>
      </div>
      <h2 class="text-xl font-bold text-gray-800">{{ props.title }}</h2>
      <div class="text-gray-600 text-sm mt-4 flex space-x-4">
        <span>{{ props.city }}</span>
        <span>|</span>
        <span>{{ props.players }} Players</span>
        <span>|</span>
        <span>{{ props.time }} Hours</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
