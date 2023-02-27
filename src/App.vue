<template>
  <main class="wrapper">
    <DZheader></DZheader>
    <DZmain></DZmain>
  </main>
</template>

<script>
  import DZheader from './components/DZheader.vue'
  import DZmain from './components/DZmain.vue'

  export default {
    name: 'App',

    components: {
      DZheader,
      DZmain,
    }
  }

</script>

<style module lang="scss">
  .wrapper {
    margin: 0;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
</style>
