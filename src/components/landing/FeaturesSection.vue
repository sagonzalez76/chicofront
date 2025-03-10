<script lang="ts" setup>
import { ref } from 'vue';
import LineButtons from '@/components/shared/LineButtons.vue';
import LineBar from '@/components/shared/LineBar.vue';

interface Button {
  label: string;
  count?: number;
  isActive?: boolean;
}

const buttons = ref<Button[]>([
  { label: 'All Items', count: 5125, isActive: true },
  { label: 'Residential Spaces', count: 64 },
  { label: 'Sports Venues' },
  { label: 'Meeting Spaces' },
  { label: 'Vans & Buses' },
  { label: 'Cars & SUVs' },
  { label: 'Lorries & Industrial Vehicles' }
]);

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
          :classButton="'flex items-center px-4 py-2 rounded-full text-sm font-semibold transition-all bg-gray-200 hover:bg-gray-300'"
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
