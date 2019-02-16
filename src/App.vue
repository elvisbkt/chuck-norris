<template>
  <div id="app">

    <ChuckNorris msg="Chuck Norris"/>

  </div>
</template>

<script>
import ChuckNorris from './components/ChuckNorris.vue'

export default {
  name: 'app',
  components: {
    ChuckNorris
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
