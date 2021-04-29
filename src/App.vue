<template>
  <div id="app">
    <Geolocation></Geolocation>
  </div>
</template>

<script>
import Geolocation from './components/Geolocation.vue'

export default {
  name: 'App',
  components: {
    Geolocation
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
