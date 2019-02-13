<template>
  <div id="app">
    <FroststridersMain/>
  </div>
</template>

<script>
import FroststridersMain from './components/FroststridersMain.vue'

export default {
  name: 'app',
  components: {
    FroststridersMain
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
body, html {
  background-color: #454851 !important;
}
</style>
