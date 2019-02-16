<template>
  <div id="app">
    <FroststridersMain/>
    <FroststridersContent/>
  </div>
</template>

<script>
import FroststridersContent from './components/FroststridersContent.vue';
import FroststridersMain from './components/FroststridersMain.vue';

export default {
  name: 'app',
  components: {
    FroststridersContent,
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
  color: #bec4c4;
}
body, html {
  background-color: #2f2d2e !important;
  margin:0;
  padding:0;
}
</style>
