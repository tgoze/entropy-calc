<template>  
  <div id="app">    
    <EntropyCalc />
  </div>
</template>

<script>
import EntropyCalc from './components/EntropyCalc.vue'

export default {
  name: 'app',
  components: {  
    EntropyCalc
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
