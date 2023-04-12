<template>
  <div class="slide">
     <swiper
      :pagination="{
        type: 'fraction',
      }"
      :navigation="true"
      :modules="modules"
      class="mySwiper"
    >
      <swiper-slide>Slide 1</swiper-slide>
      <swiper-slide>Slide 7</swiper-slide>
      <swiper-slide>Slide 8</swiper-slide>
      <swiper-slide>Slide 9</swiper-slide>
    </swiper>
  </div>
</template>

<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles

import 'swiper/css/pagination';
import 'swiper/css/navigation';


// import required modules
import { Pagination, Navigation } from 'swiper';

  export default {
    name: 'MainFirst',
     components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Pagination, Navigation],
    };
  },
  }
</script>

<style lang="scss" scoped>
.slide{
  position: relative;
  height: 690px;
}
.swiper {
  width: 500px;
  height: 500px;
}

.swiper-slide {
  width: inherit;
  text-align: center;
  font-size: 18px;
  background: #fff;

  /* Center slide text vertically */
  display: flex;
  justify-content: center;
  align-items: center;
}

.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>