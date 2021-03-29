<template>
  <div id="app">
   <eve />
  </div>
</template>

<script>
import eve from './components/events.vue'

export default {
  name: 'App',
  components: {
    eve
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
