<script lang="ts" setup>
import { ref } from 'vue'

const props = defineProps({
  images: {
    type: Array as () => string[],
    required: true,
    default: () => []
  },
  price: {
    type: Number,
    required: true,
    default: 4100,
  },
  currency: {
    type: String,
    default: 'LKR',
  },
  title: {
    type: String,
    required: true,
    default: '',
  },
  city: {
    type: String,
    required: true,
    default: '',
  },
  time: {
    type: Number,
    required: true,
    default: 1,
  },
  players: {
    type: Number,
    required: true,
    default: 1,
  },
})

const currentImageIndex = ref(0)

const nextImage = () => {
  currentImageIndex.value = (currentImageIndex.value + 1) % props.images.length
}

const prevImage = () => {
  currentImageIndex.value = (currentImageIndex.value - 1 + props.images.length) % props.images.length
}
</script>

<template>
  <div class="border rounded-lg shadow max-w-sm bg-white relative">
    <div class="relative">
      <img :src="props.images[currentImageIndex]" alt="Property Image" class="w-full h-40 object-cover rounded-lg mb-4" />
      <button @click="prevImage" class="absolute -left-0 top-1/2 transform -translate-y-1/2  text-black p-1 rounded-full">‹</button>
      <button @click="nextImage" class="absolute -right-0 top-1/2 transform -translate-y-1/2  text-black p-1 rounded-full">›</button>
    </div>
    <div class="flex justify-end">
      <span class="bg-green-500 text-white text-sm px-3 py-1 rounded-full">For Rent</span>
    </div>
    <div class="mt-4">
      <p class="text-red-500 text-lg font-semibold">{{ props.price }} {{ props.currency }} /Month</p>
      <h2 class="text-xl font-bold text-gray-800">{{ props.title }}</h2>
      <div class="text-gray-600 text-sm mt-2 flex space-x-4">
        <span>{{ props.city }}</span>
        <span>|</span>.
        <span>{{ props.players }} Players</span>
        <span>|</span>
        <span>{{ props.time }} Hours</span>
      </div>
    </div>
  </div>
</template>
