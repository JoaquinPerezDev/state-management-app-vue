<script setup>
  import { useNumbersStore } from '../assets/stores/numbers';
import useNumbers from '../composables/useNumbers';

  const { numbers, filterNum } = useNumbersStore()
</script>

<template>
  <div>
    <h1>
      Great Grandchild Component {{ filterNum(17) }}
    </h1>
  </div>
</template>