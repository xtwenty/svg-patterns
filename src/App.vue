<template>
  <div id="app">
    <griddle :grid-width="1000" :grid-height="1000" :grid-rows="2" :grid-cols="2"  />
  </div>
</template>

<script>
import Griddle from './components/Griddle.vue';

export default {
  name: 'app',
  components: {
    Griddle
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
