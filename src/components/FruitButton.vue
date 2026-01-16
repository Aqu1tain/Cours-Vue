<template>
    <button @click="emit('click')">{{ name }}</button>
    <p>{{ current }} / {{ total }}</p>
</template>

<script setup lang="ts">
defineProps<{
  name: string
  current: number
  total: number
}>()

const emit = defineEmits<{
  click: []
}>()
</script>