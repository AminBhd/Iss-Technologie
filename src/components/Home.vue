<template>
  <div class="Swiper-container">
    <swiper
      ref="mySwiper"
      modules="modules"
      :slides-per-view="1"
      :space-between="50"
      navigation
      :pagination="{ clickable: true }"
      @slideChange="SlideChanged"
      @swiper="onSwiper"
      class="mySwiper"
      :autoplay="{
        delay: 2500,
        disableOnInteraction: false,
      }"
    >
      <swiper-slide
        class="slide"
        v-for="(pic, ind) in homeData.picsSrc"
        :key="pic"
        @slideChange="SlideChanged(ind)"
      >
        <img :src="require(`../assets/${pic}`)" alt="" />
      </swiper-slide>
    </swiper>

    <div class="slide-discription">
      <h1>{{ homeData.slideTitle }}</h1>
      <p class="slide-info">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum
        distinctio molestias impedit vitae, cum alias! Officia et nam est
        molestiae distinctio? Architecto.
      </p>
    </div>

    <div class="wave">
      <svg
        data-name="Layer 1"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1200 120"
        preserveAspectRatio="none"
      >
        <path
          d="M0,0V46.29c47.79,22.2,103.59,32.17,158,28,70.36-5.37,136.33-33.31,206.8-37.5C438.64,32.43,512.34,53.67,583,72.05c69.27,18,138.3,24.88,209.4,13.08,36.15-6,69.85-17.84,104.45-29.34C989.49,25,1113-14.29,1200,52.47V0Z"
          opacity=".25"
          class="shape-fill"
        ></path>
        <path
          d="M0,0V15.81C13,36.92,27.64,56.86,47.69,72.05,99.41,111.27,165,111,224.58,91.58c31.15-10.15,60.09-26.07,89.67-39.8,40.92-19,84.73-46,130.83-49.67,36.26-2.85,70.9,9.42,98.6,31.56,31.77,25.39,62.32,62,103.63,73,40.44,10.79,81.35-6.69,119.13-24.28s75.16-39,116.92-43.05c59.73-5.85,113.28,22.88,168.9,38.84,30.2,8.66,59,6.17,87.09-7.5,22.43-10.89,48-26.93,60.65-49.24V0Z"
          opacity=".5"
          class="shape-fill"
        ></path>
        <path
          d="M0,0V5.63C149.93,59,314.09,71.32,475.83,42.57c43-7.64,84.23-20.12,127.61-26.46,59-8.63,112.48,12.24,165.56,35.4C827.93,77.22,886,95.24,951.2,90c86.53-7,172.46-45.71,248.8-84.81V0Z"
          class="shape-fill"
        ></path>
      </svg>
    </div>
  </div>
</template>



<script>
// Swiper
// import { useSwiper } from 'swiper/vue';
import { Swiper, SwiperSlide } from "swiper/vue";

import SwiperCore, { Navigation, Pagination, A11y, Autoplay } from "swiper";

import "swiper/swiper-bundle.min.css";
import "swiper/swiper.min.css";


SwiperCore.use([Navigation, Pagination, A11y, Autoplay]);

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiper: null,
      swiperOption: {
        autoplay: {
          delay: 1000,
          disableOnInteraction: false,
        },
      },
      homeData: {
        picsSrc: ["1.jpg", "2.jpeg", "3.jpg", "4.jpg", "5.jpg"],
        titles: [
          "Informatique et bureautique",
          "Télésurveillance",
          "Réseaux informatique et téléphonique",
          "Energie Solaire",
          "Système anti intrusion",
          "Système anti incendie",
          "Sonorisation",
          `Côntrole d'accès`,
        ],
        slideTitle: "Informatique et bureautique",
      },
    };
  },

  methods: {
    SlideChanged: function () {
      this.homeData.slideTitle = this.homeData.titles[this.swiper.activeIndex];
    },
    onSwiper(swiper) {
      this.swiper = swiper;
    },
  },

  setup() {
    return {
      modules: [Navigation, Pagination, A11y, Autoplay],
    };
  },
};
</script>

<style scoped>
.Swiper-container {
  width: 100%;
  height: 89vh;
  position: relative;
}
.mySwiper {
  width: 100%;
  height: 100%;
}
.slide {
  display: flex;
  justify-content: center;
  flex-direction: column;
  /* position: relative; */
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.slide-discription {
  position: absolute;
  bottom: 2%;
  z-index: 2;
  margin-left: 3vw;
  color: #fff;
  width: 90vw;
  cursor: pointer;
}

.wave {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
  transform: rotate(180deg);
  z-index: 1;
  margin-bottom: -1px;

}

.wave svg {
  position: relative;
  display: block;
  width: calc(300% + 1.3px);
  height: 229px;
  transform: rotateY(180deg);
}
.wave .shape-fill {
  fill: #121212;
}

@media (max-width: 400px) {
  .slide-discription {
    width: 80vw;
    font-size: 14px;
  }

  .slide-discription h1 {
    font-size: 18px;
    width: 280px;
  }
}
</style>