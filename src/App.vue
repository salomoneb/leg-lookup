<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <hello></hello> -->
    <!-- <component1></component1> -->
    <chamberdropdown></chamberdropdown>
  </div>
</template>

<script>
import Hello from './components/Hello'
import chamberdropdown from './components/ChamberDropdown'
// import component1 from './components/Component1'

export default {
  name: 'app',
  components: {
    Hello, chamberdropdown
    // component1
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
