<template>
  <div id="app">
    
    <Essay/>
  </div>
</template>

<script>
import Essay from './views/Essay'

export default {
  name: 'app',
  components: {
    Essay
  }
}
</script>

<style>
#app {
  font-family: 'Effra', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
