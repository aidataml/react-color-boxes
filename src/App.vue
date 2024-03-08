<template>
  <main>
    <BoxContainer/>
  </main>
</template>

<script>
import BoxContainer from './components/BoxContainer.vue';

export default {
  name: 'App',
  components: {
    BoxContainer,
  },
};
</script>

<style>
  body {
    margin: 0;
    font-family: Avenir, Helvetica, Arial, sans-serif;
  }

  main {
    display: flex;
    align-items: center;
    min-height: 100vh;
    justify-content: center;
  }
</style>