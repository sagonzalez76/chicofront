<script lang="ts" setup>
import BrowseCategories from '@/components/landing/BrowseCategories.vue';
import NavBar from '../components/landing/NavBar.vue'
import HeroSection from '@/components/landing/HeroSection.vue';
import FeaturesSection from '@/components/landing/FeaturesSection.vue'
</script>

<template>
  <div>
    <header>
      <NavBar />
    </header>
    <main>
      <HeroSection />
      <div class="container mx-auto">
        <BrowseCategories/>
      </div>
      <div>
        <FeaturesSection />
      </div>
    </main>
  </div>
</template>
