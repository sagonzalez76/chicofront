<script lang="ts" setup>
import { ref } from 'vue';
import IconUser from '@/components/shared/icons/IconUser.vue';
import IconBars from '@/components/shared/icons/IconBars.vue';

const isOpen = ref(false);
</script>

<template>
  <nav class="bg-white p-4 shadow-md">
    <div class="container mx-auto flex justify-between items-center">
      <!-- Título a la izquierda -->
      <div class="text-black text-2xl font-extrabold">FUT CHAMPS</div>

      <!-- Menú en desktop -->
      <div class="hidden md:flex space-x-16">
        <a href="#" class="text-letters hover:text-primary font-bold">Home</a>
        <a href="#" class="text-letters hover:text-primary font-bold">Tienda</a>
        <a href="#" class="text-letters hover:text-primary font-bold">Contacto</a>
      </div>

      <!-- Icono de usuario y menú hamburguesa en móviles -->
      <div class="flex items-center text-letters">
        <span class="mx-2 font-bold hidden md:inline">Esp</span>
        <IconUser class="w-8 h-8 hidden md:inline" />
        <button @click="isOpen = !isOpen" class="md:hidden ml-4">
          <IconBars  class="w-8 h-8 text-black " />
        </button>
      </div>
    </div>

    <!-- Menú desplegable en móviles -->
    <div v-if="isOpen" class="md:hidden mt-4 bg-white shadow-md p-4 flex flex-col items-center space-y-4">
      <a href="#" class="text-letters hover:text-primary font-bold">Home</a>
      <a href="#" class="text-letters hover:text-primary font-bold">Tienda</a>
      <a href="#" class="text-letters hover:text-primary font-bold">Contacto</a>
      <div class="flex items-center">
        <span class="mx-2 font-bold">Esp</span>
        <IconUser class="w-8 h-8" />
      </div>
    </div>
  </nav>
</template>

<style scoped>
</style>
