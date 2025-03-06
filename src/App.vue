<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from '@components/HelloWorld.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
<h1 class="font-seocndary text-4xl">PAPAPAP</h1>
      <nav class="font-worksans font-bold">
        <RouterLink class="bg-primary-100" to="/">Homee</RouterLink> <br>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

</style>
