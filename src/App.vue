<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import MainDesktop from './views/ShopsDesktop.vue'
import MainMobile from './views/ShopsMobile.vue'

// reactive flag to detect mobile view
const isMobile = ref(window.innerWidth < 768)

const handleResize = () => {
  isMobile.value = window.innerWidth < 768
}

onMounted(() => {
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
})
</script>

<template>
  <component :is="isMobile ? MainMobile : MainDesktop" />
</template>
