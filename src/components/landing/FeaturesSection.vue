<script lang="ts" setup>
import { ref } from 'vue';
import LineButtons from '@/components/shared/LineButtons.vue';
import LineBar from '@/components/shared/LineBar.vue';
import BaseCard from '../shared/Base/BaseCard.vue';

interface Button {
  label: string
  classButtonCustom: string
  iconClassCustom: string
  classLabel?: string
  icon?: string
  onClick: () => void
}

const buttons: Button[] = [
  {
    classButtonCustom: '',
    iconClassCustom: 'w-8 h-8 bg-red-100 mr-4 rounded-full text-primary p-1',
    label: 'Holiday Rentals',
    onClick: () => {
      console.log('Fields')
    },
  },
  {
    classButtonCustom: '',
    iconClassCustom: 'w-8 h-8 bg-green-100 mr-4 rounded-full text-green-600 p-1',
    label: 'Residential Spaces',
    onClick: () => {
      console.log('Mvp')
    },
  },
  {
    classButtonCustom: '',
    iconClassCustom: 'w-8 h-8 bg-purple-100 mr-4 rounded-full text-purple-600 p-1',
    label: 'Event Spaces',
    onClick: () => {
      console.log('Teams')
    },
  },
  {
    classButtonCustom: '',
    iconClassCustom: 'w-8 h-8 bg-blue-100 mr-4 rounded-full text-sky-600 p-1',
    label: 'Commercial Properities',
    onClick: () => {
      console.log('Teams')
    },
  },
  {
    classButtonCustom: '',
    iconClassCustom: 'w-8 h-8 bg-orange-100 mr-4 rounded-full text-orange p-1',
    label: 'More',
    onClick: () => {
      console.log('Teams')
    },
  },
]

const containerRef = ref<HTMLElement | null>(null);

const scrollLeft = () => {
  if (containerRef.value) {
    containerRef.value.scrollBy({ left: -200, behavior: 'smooth' });
  }
};

const scrollRight = () => {
  if (containerRef.value) {
    containerRef.value.scrollBy({ left: 200, behavior: 'smooth' });
  }
};

const cards = ref([
  {
    images: ['../images/Stadium1.jpg','../images/Stadium2.jpg'],
    price: 85000,
    currency: 'COL',
    title: 'Luxury villa in Rego Park',
    city: 'Popayán',
    time: 1,
    players: 11,
  },
  {
    images: ['../images/Stadium1.jpg','../images/Stadium2.jpg'],
    price: 75000,
    currency: 'COL',
    title: 'Modern apartment in Cali',
    city: 'Cali',
    time: 2,
    players: 8,
  },
  {
    images: ['../images/Stadium1.jpg','../images/Stadium2.jpg'],
    price: 65000,
    currency: 'COL',
    title: 'Cozy house in Medellín',
    city: 'Medellín',
    time: 3,
    players: 5,
  },
  {
    images: ['../images/Stadium1.jpg','../images/Stadium2.jpg'],
    price: 65000,
    currency: 'COL',
    title: 'Cozy house in Medellín',
    city: 'Medellín',
    time: 3,
    players: 5,
  },
  {
    images: ['../images/Stadium1.jpg','../images/Stadium2.jpg'],
    price: 65000,
    currency: 'COL',
    title: 'Cozy house in Medellín',
    city: 'Medellín',
    time: 3,
    players: 5,
  },
  {
    images: ['../images/Stadium1.jpg','../images/Stadium2.jpg'],
    price: 65000,
    currency: 'COL',
    title: 'Cozy house in Medellín',
    city: 'Medellín',
    time: 3,
    players: 5,
  },
  {
    images: ['../images/Stadium1.jpg','../images/Stadium2.jpg'],
    price: 65000,
    currency: 'COL',
    title: 'Cozy house in Medellín',
    city: 'Medellín',
    time: 3,
    players: 5,
  },
]);
</script>

<template>
  <section class="relative max-w-screen-lg mx-auto px-6">
    <h2 class="text-center font-bold text-4xl mt-24">Featured Listings</h2>
    <!-- Indicador superior -->
    <LineBar />

    <div class="relative flex items-center">
      <!-- Botón de desplazamiento izquierdo -->
      <button 
        @click="scrollLeft" 
        class="mr-2 p-2 bg-gray-300 rounded-full hover:bg-gray-400"
      >
        ◀
      </button>
      
      <!-- Contenedor scrollable -->
      <div
        ref="containerRef"
        class="flex gap-4 overflow-x-auto scrollbar-hide whitespace-nowrap px-2 py-2"
        style="scroll-behavior: smooth;"
      >
        <LineButtons
          :buttons="buttons"
          :classContainer="'flex gap-4 overflow-x-auto scrollbar-hide whitespace-nowrap px-2 py-2'"
          :classButton="'flex items-center px-4 py-2 rounded-full text-sm font-semibold transition-all bg-gray-200 hover:bg-primary hover:text-white'"
          :classLabel="''"
        />
      </div>
      
      <!-- Botón de desplazamiento derecho -->
      <button 
        @click="scrollRight" 
        class="ml-2 p-2 bg-gray-300 rounded-full hover:bg-gray-400"
      >
        ▶
      </button>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 mt-8">
      <BaseCard
        v-for="(card, index) in cards"
        :key="index"
        :images="card.images"
        :price="card.price"
        :currency="card.currency"
        :title="card.title"
        :city="card.city"
        :time="card.time"
        :players="card.players"
      />
    </div>
  </section>
</template>

<style scoped>
/* Ocultar scrollbar */
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}
.scrollbar-hide {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>