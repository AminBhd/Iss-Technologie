<template>
  <div id="app" v-on="watchScrolling">
    <HeaderApp/>
    <HomeApp/>
  </div>
</template>

<script>
import HeaderApp from './components/Header.vue'
import HomeApp from './components/Home.vue'

export default {
  name: 'App',
  components: {
    HeaderApp,
    HomeApp
  },
  data() {
    return {
      topOfPage: false
    }
  },

  methods: {
    watchScrolling (e) {
      console.log(e.target);
      if(window.scrollY == 0) this.topOfPage = false
      else this.topOfPage = true
    }

  },
}
</script>

<style>
body{
  margin: 0px;
  padding: 0;
  background-color: #28235D;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
    height: 300vh;

}
</style>

