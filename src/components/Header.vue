<template>

    <nav class="navbar navbar-expand-sm sticky-top py-4" id="header">
      <div class="container">
        <div class="logo">
          <img :src="require(`../assets/${logoSrc}`)" alt="" />
        </div>
        <button
          class="navbar-toggler navbar-toggler-right"
          type="button"
          data-toggle="collapse"
          data-target="#navbar1"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse nav-list" id="navbar1">
          <ul class="navbar-nav">
            <li

              class="nav-item"
              v-for="(list, index) in navList"
              :key="index"
            >
              <a href="#" :class="{active: navList[`${index}`]}" >{{ index }}</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
</template>

<script>
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";

export default {
  name: "Header",

  data() {
    return {
      logoSrc: "logo.png",
      navList: {
        "Home": true,
        "About": false,
        "Services": false,
        "Contact": false},
      headerPos: null,
    };
  },

  created() {
    window.addEventListener("scroll", this.handleScroll);
  },

  mounted() {
    this.headerPos = this.$el;

  },
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },

  methods: {
    handleScroll() {
      // console.log(this.headerPos.getBoundingClientRect().top);
      if (this.headerPos.getBoundingClientRect().top == 0) {
        document.documentElement.setAttribute("class", "stuck");
      } else document.documentElement.removeAttribute("class");
    },
  },
};
</script>





<style scoped>
#header{
  background-color: #121212;
}

img {
  width: 64px;
  height: 60px;
  margin-left: 2.5rem;
}

.nav-list {
  position: absolute;
  left: 35%;
  color: #fff;
  font-size: 18px;
  font-weight: 500;
}

onScroll {
  height: 75px;
  /* transition: all ease 0.5s; */
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  position: relative;
  padding: 0 20px;
}

a {
  text-decoration: none;
  color: #fff;
  transition: all ease .5s;
}

a:hover {
  color: #3DA0E3 !important;
  transition: all ease .5s;
}

a:hover::after {
  position: absolute;
  content: '';
  width: 0;
  height: 2px;
  background-color: #3DA0E3;
  bottom: -4px;
  z-index: 99;
  left: 20px;
}

a.active::after {
  position: absolute;
  content: '';
  width: 70%;
  height: 2px;
  background-color: #3DA0E3;
  bottom: -4px;
  z-index: 99;
  left: 20px;
}

a:hover::after {
  position: absolute;
  content: '';
  width: 30%;
  height: 2px;
  background-color: #3DA0E3;
  bottom: -4px;
  z-index: 99;
  left: 20px;
  transition: width ease 1s;
}

.active {
  color: #3DA0E3 !important;
}

.sticky-top {
    transition: all 0.25s ease-in;
}

/* style for when sitcky is applied */
.stuck .navbar.sticky-top {
    background: linear-gradient(90deg,#888888, #121212,#121212) !important;
    padding-top: .8rem !important;
    padding-bottom: .8rem !important;
    box-shadow: 1px 1px 5px rgba(255, 255, 255, 0.57);
}
</style>
