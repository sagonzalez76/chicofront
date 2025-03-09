<script lang="ts" setup>
import LineButtons from '@/components/shared/LineButtons.vue'

interface Button {
  label: string
  classButtonCustom: string
  classLabel?: string
  icon?: string
  onClick: () => void
}

const buttons: Button[] = [
  {
    classButtonCustom: 'bg-yellow-500',
    classLabel: 'text-red-500',
    label: 'Fields',
    icon: 'IconHome',
    onClick: () => {
      console.log('Fields')
    },
  },
  {
    classButtonCustom: 'bg-blue-500',
    label: 'Mvp',
    icon: 'IconHome',
    onClick: () => {
      console.log('Mvp')
    },
  },
  {
    classButtonCustom: 'bg-red-500',

    label: 'Teams',
    icon: 'IconHome',
    onClick: () => {
      console.log('Teams')
    },
  },
]
</script>

<template>
  <section class="browse-categories">
    <h2 class="text-center font-bold text-4xl mt-24">Browse From Top Categories</h2>
    <div class="categories-container flex justify-center gap-24 m-10">
      <LineButtons
        :buttons="buttons"
        :classContainer="'flex font-bold py-1 px-4 rounded-full bg-black text-white  hover:text-white'"
        :classButton="'flex font-bold py-1 px-4 rounded-full bg-blue-500 text-white hover:bg-primary-dark hover:text-white'"
      />
    </div>
  </section>
</template>
