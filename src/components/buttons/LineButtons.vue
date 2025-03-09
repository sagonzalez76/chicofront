<template>
  <div class="flex justify-center gap-3 m-5">
    <button
      v-for="(button, index) in props.buttons"
      :key="index"
      :class="[
        'font-bold py-1 px-4 rounded-full',
        button.bgColor,
        button.textColor,
        button.hoverBgColor,
        button.hoverTextColor
      ]"
      @click="button.onClick"
    >
      {{ button.label }}
    </button>
  </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue'

interface Button {
  label: string
  onClick: () => void
  bgColor: string
  textColor: string
  hoverBgColor: string
  hoverTextColor: string
}

const props = defineProps<{
  buttons: Button[]
}>()
</script>

<style scoped></style>