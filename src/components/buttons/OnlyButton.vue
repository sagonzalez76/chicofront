<template>
  <button
    :class="buttonClass"
    @click="props.onClick"
  >
  <span :class="textClass">{}</span>
  </button>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue'

interface Button {
  text: string
  buttonClass: string  
}

const props = defineProps<{
  buttons: Button,
  buttonClass: {
    type: string,
    default: 'font-bold py-1 px-4 rounded-full bg-primary text-white hover:bg-primary-dark hover:text-whitefont-bold py-1 px-4 rounded-full bg-primary text-white hover:bg-primary-dark hover:text-white'     
  }
  onClick: () => void
  text: {
    type: string,
    default: 'Click Me'
  }
  textClass: {
    type: string,
    default: 'text-white'
  }
}>()

</script>