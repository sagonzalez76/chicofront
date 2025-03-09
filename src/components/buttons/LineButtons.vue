<template>
  <button
    v-for="(button, index) in props.buttons"
    :key="index"
    :class="[
      button.classButton,
      button.bgColor,
      button.textColor,
      button.hoverBgColor,
      button.hoverTextColor,
      button.borderRadious,
      button.border
    ]"
    @click="button.onClick"
  >
    <!-- Renderizar el icono si existe con sus estilos personalizados -->
    <BaseIcon 
      v-if="button.icon" 
      :name="button.icon"
      :size="button.iconSize"
      :color="button.iconColor"
      :class="button.iconMargin"
      :bg="button.iconBg"
      :rounded="button.iconRounded"
      :padding="button.iconPadding"
    />
    
    {{ button.label }}
  </button>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue'
import BaseIcon from '../icons/IconBase.vue'

interface Button {
  classButton?: string
  label: string
  onClick: () => void
  bgColor: string
  textColor: string
  hoverBgColor?: string
  hoverTextColor?: string
  borderRadious?: string
  border?: string
  icon?: string // Ahora solo pasamos el nombre del icono
  iconSize?: string // Tamaño del icono
  iconColor?: string // Color del icono
  iconMargin?: string // Espaciado del icono
  iconBg?: string // Fondo del icono
  iconRounded?: string // Borde redondeado del botón
  iconPadding?: string // Relleno del botón
}

const props = defineProps<{
  buttons: Button[]
  classButton: {
    type: string,
    default: 'font-bold py-1 px-4 rounded-full bg-primary text-white hover:bg-primary-dark hover:text-white'
  }
}>()
</script>

<style scoped></style>
