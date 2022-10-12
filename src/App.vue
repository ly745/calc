<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <calc/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import calc from './components/calc.vue'
export default {
  name: 'App',
  components: {
    HelloWorld,
    calc
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
