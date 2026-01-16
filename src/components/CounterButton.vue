<template>
  <button @click="index++">{{ currentFruit }}</button>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const fruits = ['banana', 'orange', 'apple', 'dragon fruit']
const index = ref(0)

const currentFruit = computed(() => fruits[index.value % fruits.length])
</script>