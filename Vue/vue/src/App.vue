<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
  
    <AsPort></AsPort>
  </div>
</template>

<script>

import AsPort from  './components/123.vue'

export default {
  name: 'App',
  components: {
    AsPort
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
