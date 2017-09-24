<template>
  <div id="app">
    <chamberdropdown></chamberdropdown>
  </div>
</template>

<script>
import chamberdropdown from './components/ChamberDropdown'

export default {
  name: "app",
  components: {
    chamberdropdown
  }
}
</script>

<style>

.chamber-selection, .committee-selection, .committee-results {
  display: flex;
  align-items: baseline;
  font-family: 'Avenir', Helvetica, Arial, sans-serif; 
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.chamber-selection {
  flex-direction: column;
}
.committee-results {
  flex-direction: column;
}
</style>
