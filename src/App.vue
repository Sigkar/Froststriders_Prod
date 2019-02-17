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
 @import url('https://fonts.googleapis.com/css?family=Nunito:400,700');
* {
  color: #fceff9;
  font-family: 'Nunito', Arial, Helvetica, sans-serif;
  text-transform:uppercase;
  font-weight:400;
}
h1{font-size:32px; font-weight:700;}
h2{font-size:28px;}
h3{font-size:25px;}
p,li,h4{font-size:22px;}
h5{font-size:16px;}
h6{font-size:12px;}
#app {
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
