<template>
    <button @click="emit('next')">{{ name }}</button>
    <p>{{ current }} / {{ total }}</p>
</template>

<script setup lang="ts">
defineProps<{
  name: string
  current: number
  total: number
}>()

const emit = defineEmits<{
  next: []
}>()
</script>