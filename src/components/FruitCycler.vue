<template>
  <img :src="currentFruit.image" :alt="currentFruit.name" />
  <FruitButton
    :name="currentFruit.name"
    :current="currentIndex + 1"
    :total="fruits.length"
    @click="next"
  />
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import FruitButton from './FruitButton.vue'

interface Fruit {
  name: string
  image: string
}

const fruits: Fruit[] = [
  { name: 'banana', image: 'https://upload.wikimedia.org/wikipedia/commons/2/2c/Banana_on_black_background.jpg' },
  { name: 'orange', image: 'https://media.istockphoto.com/id/477836156/fr/photo/orange-fruits-isol%C3%A9-sur-blanc.jpg?s=612x612&w=0&k=20&c=Qw_SKI4glq0hjhmvmRCoLsh27VWax5Bh7ehrzSSIQXE=' },
  { name: 'apple', image: 'https://m.media-amazon.com/images/I/81Dl5GdAVkL.png' },
  { name: 'dragon fruit', image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/Pitaya_P1190424.jpg/330px-Pitaya_P1190424.jpg' }
]
const index = ref(0)

const currentIndex = computed(() => index.value % fruits.length)
const currentFruit = computed((): Fruit => fruits[currentIndex.value]!)

const next = () => { index.value++ }
</script>

<style scoped>
img {
  width: 200px;
  height: 200px;
  object-fit: cover;
}
</style>
