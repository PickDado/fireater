<template>
  <div id="app">
    
    <DataSelector />
  </div>
</template>

<script>
//import Mappa from './components/Mappa.vue'
import DataSelector from "./components/DataSelector.vue"

export default {
  name: 'App',
  components: {
    DataSelector
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
  margin-top: 15px;
}
</style>
