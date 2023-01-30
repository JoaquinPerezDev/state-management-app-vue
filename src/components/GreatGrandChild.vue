<script setup>
  import useNumbers from '../composables/useNumbers';

  const { numbers, filterNum } = useNumbers()
</script>

<template>
  <div>
    <h1>
      Great Grandchild Component {{ filterNum(5) }}
    </h1>
  </div>
</template>