<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <secondCalc/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
// import calc from './components/calc.vue'
import secondCalc from './components/secondCalc.vue'
export default {
  name: 'App',
  components: {
    HelloWorld,
    // calc,
    secondCalc
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
