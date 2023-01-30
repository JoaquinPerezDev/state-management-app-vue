<script setup> 
  import GrandChild from './GrandChild.vue'
  import { inject } from "vue"

  const numbers = inject('numbers')
</script>

<template>
  <div>
    <h1>
      Child Component {{ numbers }}
    </h1>
    <div class="line"></div>
    <GrandChild />
  </div>
</template>