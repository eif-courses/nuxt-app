<script setup lang="ts">

interface CardType {
  title?: string
  description?: string
  imagesUrls?: Array<string>
}
const props = defineProps<CardType>()

function randomImage(){
  //return props.imagesUrls[1];
  return props.imagesUrls[Math.floor(Math.random()*props.imagesUrls.length)];
}

</script>

<template>
  <div class="cardClass">
    <img class="responsiveImage" :src="randomImage" alt="">
    <h3>{{ title }}</h3>
    <p> {{ description }}</p>
    <button @click="randomImage">Next Image</button>
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
