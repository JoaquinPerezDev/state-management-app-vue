<script setup>
  import { inject } from "vue"

const numbers = inject('numbers')
</script>

<template>
  <div>
    <h1>
      Great Grandchild Component {{ numbers }}
    </h1>
  </div>
</template>