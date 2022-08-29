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
        <h1>#know Us</h1>
      </div>
    </div>

    <div class="about-description">
      <h1>Vente, Étude et Installation</h1>
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Harum
        blanditiis aperiam nesciunt quisquam obcaecati sequi, reiciendis, eaque
        eos deleniti facere nobis iure quas soluta ex mollitia facilis minus
        ipsam sunt! Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Quos nobis eveniet nemo magni tenetur. Ex a dolorum officiis minus earum
        est iusto ipsam quas, nostrum ducimus veniam, unde, voluptate vero!
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

export default {};
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
  width: 100%;
  height: auto;
  align-items: center;
  position: relative;
}

.know-us {
  width: 400px;
  height: auto;
  color: #ffffff;
  text-align: center;
  margin-top: 5vw;
}

.know-us h1 {
  font-size: 5.5em;
  font-weight: 500;
}

.logo-container {
  width: 400px;
  display: flex;
}

.logo {
  width: 70%;
  height: auto;
  margin: auto;
}

.about-description {
  width: 80%;
  height: auto;
  max-width: 950px;
  margin-top: 6vh;
  margin-left: auto;
  margin-right: auto;
  color: #ffffff;
}

/* .about-description h1{
  font-size: 4.5vmin	;
} */

.bottom-line {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
  margin-bottom: -1px;
}

.bottom-line svg {
  position: relative;
  display: block;
  width: calc(300% + 1.3px);
  height: 249px;
}

.bottom-line .shape-fill {
  fill: #3DA0E3;
}

@media (max-width: 800px) {
  .know-us h1 {
    font-size: 3em;
  }
}

</style>