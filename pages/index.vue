<script setup lang="ts">


const counter = ref(0)
let images: Array<string> = ['https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR7XYB40mH1m7iTKa9IZ7Y8L2bNZhJRgVvfQOIFPPi_OQelhq00LmskqKieCo-FVtNfCuo&usqp=CAU',
  'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSkN5dfV0qZ5JsSBgj8NVJRb3bABV5C_1DE9v0vIzIo7Pw8WajZLlMMsE238sPLKXdUXJU&usqp=CAU',
  'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT4OgGyu2-dFSpvDYmwpa2Ks0d6a_KTbAhJ8u9KaF2h-eA7KRJJQqy3lhRgo9MfayM3nRE&usqp=CAU']


function increment(){
  counter.value++;
}

</script>

<template>

  <CardItem
      title="My card"
      description="Here is really long description for card :)"
      :images-urls="images"
      @change="counter = 1000"
  />




<h1 v-if="counter < 10">{{ counter }}</h1>
  <h1 v-else>WE DONE!</h1>
  <button @click="counter++">Click to increment</button>
</template>

<style scoped>
.active{
  color: green;
}
.text-danger{
  color: blue;
}
</style>
