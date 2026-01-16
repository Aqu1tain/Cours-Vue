<template>
  <FruitCycler v-for="selector in selectors" :key="selector.id" />
</template>

<script setup lang="ts">
import FruitCycler from './components/FruitCycler.vue'

const selectors = [
  { id: 1 },
  { id: 2 },
  { id: 3 }
]
</script>
