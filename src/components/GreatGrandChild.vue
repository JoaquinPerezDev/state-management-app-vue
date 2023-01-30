<script setup>
  import { defineProps } from 'vue';

const { numbers } = defineProps(['numbers'])
</script>

<template>
  <div>
    <h1>
      Great Grandchild Component {{ numbers }}
    </h1>
  </div>
</template>