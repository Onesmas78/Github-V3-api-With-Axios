<template>
  <div id="app">
    <github></github>
  </div>
</template>

<script>
import github from './components/github.vue'

export default {
  name: 'app',
  components: {
    github
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
