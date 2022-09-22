<script setup lang="ts">

import { ref } from "#imports";

interface CardType {
  title?: string
  description?: string
  imagesUrls?: Array<string>
}
const props = defineProps<CardType>()
const image = ref('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRtBF1IDUf54FMZod7KsnwJ2fqhFCRVfNuq56c6S6W_fONH1XLf3b2uWk_ot3FSU7pkNKw&usqp=CAU')


const emit = defineEmits<{
  (e: 'change', id: number): void
  (e: 'update', value: string): void
}>()




function randomImage(){
  return props.imagesUrls[Math.floor(Math.random()*props.imagesUrls.length)];
}

</script>

<template>
  <div class="cardClass">
    <img class="responsiveImage" :src="image" alt="">
    <h3>{{ title }}</h3>
    <p> {{ description }}</p>
    <button @click="image = randomImage()">{{ randomImage() }}</button>
    <button @click="emit('change', 9)">Text we get from Parent Component click </button>
  </div>
</template>


<style scoped>
.cardClass {
  width: 200px;
  border: 1px solid aqua;
  background: aliceblue;
  text-align: center;
}

.responsiveImage {
  width: 200px;
}
</style>
