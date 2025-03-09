<script lang="ts" setup>
import LineButtons from '../buttons/LineButtons.vue'

const buttons = [
  {
    label: 'Holiday Rentals',
    onClick: () => console.log('Inicio'),
    bgColor: 'transparent',
    textColor: 'text-black',
    border: 'border border-radius',
    icon: 'IconLike', // Solo pasamos el nombre del archivo sin importar
    iconSize: '8',
    iconColor: 'text-red-500',
    iconPadding: 'p-2',
    iconBg: 'bg-red-100',
    iconRounded: 'rounded-full',
  },
  {
    label: 'Residential Spaces',
    onClick: () => console.log('Carrito'),
    bgColor: 'transparent',
    textColor: 'text-black',
    border: 'border border-radius',
    icon: 'IconHome',
    iconSize: '8',
    iconColor: 'text-green-500',
    iconPadding: 'p-2',
    iconBg: 'bg-green-100',
    iconRounded: 'rounded-full',
  },
  {
    label: 'Event Spaces',
    onClick: () => console.log('Dinero'),
    bgColor: 'transparent',
    textColor: 'text-black',
    border: 'border border-radius',
    icon: 'IconTooling',
    iconSize: '8',
    iconColor: 'text-purple-600',
    iconPadding: 'p-2',
    iconBg: 'bg-purple-100',
    iconRounded: 'rounded-full',
  },
  {
    label: 'Commercial Properities',
    onClick: () => console.log('Dinero'),
    bgColor: 'transparent',
    textColor: 'text-black',
    border: 'border border-radius',
    icon: 'IconDollar',
    iconSize: '8',
    iconColor: 'text-blue-600',
    iconPadding: 'p-2',
    iconBg: 'bg-blue-100',
    iconRounded: 'rounded-full',
  },
  {
    label: 'More',
    onClick: () => console.log('Dinero'),
    bgColor: 'transparent',
    textColor: 'text-black',
    border: 'border border-radius',
    icon: 'IconBars',
    iconSize: '8',
    iconColor: 'text-orange-600',
    iconPadding: 'p-2',
    iconBg: 'bg-orange-100',
    iconRounded: 'rounded-full',
  },
]
</script>

<template>
  <section class="browse-categories">
    <h2 class="text-center font-bold text-4xl mt-24">Browse From Top Categories</h2>
    <div class="categories-container flex justify-center gap-24 m-10">
      <LineButtons :buttons="buttons" classButton="'font-bold py-1 px-4 rounded-full bg-primary text-white hover:bg-primary-dark hover:text-white'"/>
    </div>
  </section>
</template>
