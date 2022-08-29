<template>
  <div id="About">
    <div class="about-cover">
      <img src="../assets/about-cover.jpg" alt="" />
      <div class="background"></div>
    </div>
    <div class="about-container">
      <div class="logo-container">
        <img class="logo" src="../assets/logo.png" alt="" />
      </div>
      <div class="know-us">
        <h1>#Know Us</h1>
      </div>
    </div>
    <div class="about-description">
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Harum
        blanditiis aperiam nesciunt quisquam obcaecati sequi, reiciendis,
        eaque eos deleniti facere nobis iure quas soluta ex mollitia facilis
        minus ipsam sunt!
      </p>
    </div>

    <div class="bottom-line">
      <svg
        data-name="Layer 1"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1200 120"
        preserveAspectRatio="none"
      >
        <path
          d="M598.97 114.72L0 0 0 120 1200 120 1200 0 598.97 114.72z"
          class="shape-fill"
        ></path>
      </svg>
    </div>
  </div>
</template>



<script>

import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";

export default {

};
</script>



<style scoped>
#About {
  width: 100%;
  height: 100vh;
  position: relative;
  background-color: #121212;
}

.about-cover {
  width: 100%;
  height: 35%;
  position: absolute;
  top: 2%;
  left: 0;
  overflow: hidden;
  display: flex;
}

.about-cover img {
  width: auto;
  min-width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0.6;
  margin-bottom: 11vh;
}

.background {
  background-color: #3da1e37d;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.about-container {
  padding-top: 1vw;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: space-evenly;
  position: absolute;
  width: 100%;
  height: auto;
  align-items: center;
}

.know-us {
  width: 400px;
  height: auto;
  color: #ffffff;
  text-align: center;
  margin-top: 5vw;

}

.know-us h1 {
  font-size: 6vw;
  font-weight: 500;
}

.logo-container {
    width: 400px;
    display: flex;
    margin-top: 2vw;
}

.logo {
    width: 70%;
  height: auto;
  margin: auto;
}

.about-description {
  width: 80%;
  height: 30%;
  padding-top: 35%;
  box-shadow: 1px 1px 5px rgba(255, 255, 255, 0.57);
}

.bottom-line {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
}

.bottom-line svg {
  position: relative;
  display: block;
  width: calc(300% + 1.3px);
  height: 249px;
}

.bottom-line .shape-fill {
  fill: #ffffff;
}
</style>