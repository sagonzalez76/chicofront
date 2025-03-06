<script lang="ts" setup>
import NavBar from '../components/landing/NavBar.vue'
import HeroSection from '@/components/landing/HeroSection.vue';
</script>

<template>
  <div>
    <header>
      <NavBar />
    </header>
    <main>
      <HeroSection />
      <div class="container mx-auto">
        <h1 class="text-4xl font-bold mt-8">Bienvenido a Mi Sitio</h1>
        <p class="text-lg mt-4">
          Este es un sitio de ejemplo para mostrar cómo se puede usar Vue 3 con Vite y Tailwind CSS.
        </p>
      </div>
    </main>
  </div>
</template>
