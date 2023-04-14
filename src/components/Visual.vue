<template>
  <div class="wrap_visual">
    <!-- :autoplay="{ delay: 2000, disableOnInteraction: true, pauseOnMouseEnter: true, }"  -->
     <swiper
      :pagination="{type: 'fraction'}"
      :navigation="{ prevEl: '.swiper-button-prev', nextEl: '.swiper-button-next' }"
      :loop="true"
      :autoplay="{ delay: 5000, }" 
      :modules="modules"
      class="mySwiper_visual"
    >
      <swiper-slide v-for="e in 6" :key="e">
        <img :src="require(`@/assets/images/main_visual_swipe${e}.png`)" :alt="`배너`">
      </swiper-slide>
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>
      <div class="swiper-pagination"></div>
    </swiper>
    <!-- <div>
      <button >시작</button>
      <button >중지</button>
    </div> -->
  </div>
</template>

<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide, } from 'swiper/vue';
// import required modules
import { Pagination, Navigation, Autoplay } from 'swiper';

// Import Swiper styles
import 'swiper/css'
import 'swiper/css/pagination';
import 'swiper/css/navigation';



  export default {
    name: 'VisualView',
     components: {
      Swiper,
      SwiperSlide,
  },
  setup() {
    return {
      modules: [Pagination, Navigation, Autoplay]
    };
  },
  data() {
    return {
    }
  },
  }
</script>

<style lang="scss">
.mySwiper_visual{
  position: relative;
  height: 690px;
  .swiper-button-next, .swiper-button-prev{
    color: white;
  }
  .swiper-button-prev{
    margin-left: 110px;
  }
  .swiper-button-next{
    margin-right: 110px;
  }
  // 중복 문제로 인하여 scss 말고 일반 css 로 적용
  // .swiper-pagination{
  //   background-color: transparent;
  //   width: 5%;
  //   left: calc(50% - 680px);
  //   bottom: 165px;
  //   color: #fff;
  //   font-size: 20px;
  //   line-height: 46px;
  //   letter-spacing: -0.2px;
  // }
  /* 아래는 swiper 가지고 온 그대로 */
  .swiper {
    width: 100%;
    height: 100%;
  }
  .swiper-slide {
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
  
}




</style>
<style>
/* 중복문제 때문에 scss 안에서 뺌 */
.mySwiper_visual .swiper-pagination{
    background-color: transparent;
    width: 5%;
    left: calc(50% - 680px);
    bottom: 165px;
    color: #fff;
    font-size: 20px;
    line-height: 46px;
    letter-spacing: -0.2px;
  }


</style>