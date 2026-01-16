<template>
  <FruitButton
    :name="currentFruit"
    :current="currentIndex + 1"
    :total="fruits.length"
    @next="next"
  />
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import FruitButton from './FruitButton.vue'

const fruits = ['banana', 'orange', 'apple', 'dragon fruit']
const index = ref(0)

const currentIndex = computed(() => index.value % fruits.length)
const currentFruit = computed(() => fruits[currentIndex.value]!)

const next = () => { index.value++ }
</script>
