<template>
  <div id="app">
    <SearchEngine/>
  </div>
</template>

<script>
import SearchEngine from './components/SearchEngine.vue'

export default {
  name: 'app',
  components: {
    SearchEngine
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
