<script setup>
  import Parent from './components/Parent.vue'
  import { ref, provide } from 'vue';

  const numbers = ref([1,2,3,4,5,6,7,8,9])

  //NOTE ON PROP DRILLING: Prop drilling is the idea of passing down props from the 
  //top-most level(Parent) through every level including the nested component we need 
  //the props for(Great grandchild). We can accomplish this by declaring the ref in each
  //level then including :numbers="numbers" within the component tag of the child component.
  //In the case of our App, you can see below the Parent component is given access to the 
  //numbers, which then opens the possibility for the Parent's child components to receive 
  //the numbers as props as well. The big flaw to this approach is the repeatable nature. 
  //If the props were to be modified in the App view, we would need to modify them at every
  //level as well. There are better ways to accomplish giving access to nested components 
  //without the need to repeat and duplicate.

  //PROVIDE/INJECT: This method allows you to set the 'provide' at the top level App view.
  //This allows us to then 'inject' those props directly to the components we're wanting to 
  //provide them to. The big downside to using this approach is that you have to duplicate 
  //logic at each component you're wanting to 'inject' into. This of course is not ideal, 
  //since it goes against the DRY(Don't Repeat Yourself) ideology of writing code.  

  provide("numbers", numbers)
</script>

<template>
  <main>
    <Parent  />
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
