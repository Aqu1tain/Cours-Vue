<template>
  <button @click="index = (index + 1) % fruits.length">{{ fruits[index] }}</button>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const fruits = ['banana', 'orange', 'apple', 'dragon fruit']
const index = ref(0)
</script>