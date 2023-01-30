<script setup>
  import { ref, reactive } from 'vue';

  // const red = ref(0)
  // const green = ref(0)
  // const blue = ref(0)

  // const color = ref({
  //   red: 0,
  //   green: 0,
  //   blue: 0
  // })

  //NOTE: Ref can take any value whereas reactive only takes in objects. This can be used 
  //as a point of distinction for when to use one or the other. 
  //The other difference is to access values using ref, we utilize '.value' whereas when using
  //reactive you can access state directly.
  //The last difference is with ref you can update the entire object whereas with reactive you
  //can only update properties.

  const color = reactive({
    red: 0,
    green: 0,
    blue: 0
  })

  const selectRandomColor = () => {
    color.red = Math.floor(Math.random() * 255);
    color.green = Math.floor(Math.random() * 255);
    color.blue = Math.floor(Math.random() * 255);
  }
</script>

<template>
<main :style="{backgroundColor: `rgb(${color.red}, ${color.green}, ${color.blue})`}">
  <div>
    <input type="number" v-model="color.red" placeholder="red">
    <input type="number" v-model="color.green" placeholder="green">
    <input type="number" v-model="color.blue" placeholder="blue">
    <button @click="selectRandomColor">Select Random Color</button>
  </div>
</main>
</template>

<style scoped>
  main {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  div {
    display: flex;
    flex-direction: column;
  }
</style>
