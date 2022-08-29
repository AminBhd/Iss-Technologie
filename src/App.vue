<template>
  <div id="app">
    <HomeApp />
    <HeaderApp ref="header" />
    <AboutApp/>
    <ServicesApp/>
  </div>
</template>





<script defer>
import HeaderApp from "./components/Header.vue";
import HomeApp from "./components/Home.vue";
import AboutApp from './components/About.vue'
import ServicesApp from './components/Services.vue'

import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";

export default {
  name: "App",
  components: {
    HeaderApp,
    HomeApp,
    AboutApp,
    ServicesApp,
  },

  data() {
    return {};
  },


  methods: {
  },
};
</script>






<style>
* {
    padding: 0;
    margin: 0;
}

body {
  margin: 0px;
  padding: 0;
  background-color: #121212;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 300vh;
}


</style>

