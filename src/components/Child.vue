<script setup> 
  import GrandChild from './GrandChild.vue'
  import { useNumbersStore } from '../assets/stores/numbers';

  const {numbers, addNumber} = useNumbersStore()
</script>

<template>
  <div>
    <h1>
      Child Component {{ numbers }}
    </h1>
    <button @click="addNumber(4)">Add Number</button>
    <div class="line"></div>
    <GrandChild />
  </div>
</template>