<template>
  <div id="header">

    <div class="logo">
      <img :src="require(`../assets/${logoSrc}`)" alt="">
    </div>
    <div class="nav-list" :class="{onScroll: topOfPage }" >
      <ul>
        <li v-for="(list, index) in navList" :key="index">{{ list }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
  },
  data() {
    return {
      logoSrc: 'logo.png',
      navList: ['Home', 'About', 'Services', 'Contact'],
      topOfPage: window.scrollY,
      pageY: false,
    }
  },

  mounted() {
      console.log(this.topOfPage)
    
  },

  methods: {
    onTopOfPage: () => {
      console.log(this.topOfPage)
    }
  },

  watch: {
    topOfPage(x) {
      console.log(x);
    },
    // pageY: function(y) {
    //   this.pageY = y;
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#header{
  height: 65px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  margin-bottom: 2px;
  background: linear-gradient(-90deg, #121212, #676767);
  z-index: 100;
  position: fixed;
}

img{
  width: 64px;
  height: 60px;
  margin-left: 2.5rem;
}

.nav-list{
  position: absolute;
  left: 35%;
  color: #fff;
  font-size: 18px;
  font-weight: 500;
}

onScroll {
  height: 75px;
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.57);
  /* transition: all ease 0.5s; */

}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 20px;
}
a{
  text-decoration: none;
  color: #000;
}

@media (max-width: 400px) {
  .nav-list {
    display: none;
  }
}

</style>
