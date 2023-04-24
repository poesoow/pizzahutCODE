<template>
  <div class="wrap_visual">
    <!-- :autoplay="{ delay: 2000, disableOnInteraction: true, pauseOnMouseEnter: true, }"  -->
     <swiper
      :pagination="{type: 'fraction'}"
      :navigation="{ prevEl: '.swiper-button-prev', nextEl: '.swiper-button-next' }"
      :loop="true"
      @update = "onSwiperInit"
      :autoplay="isAutoplayEnabled && { delay: 5000, disableOnInteraction: true }" 
      :modules="modules"
      class="mySwiper_visual"
    >
      <swiper-slide v-for="e in 6" :key="e">
        <img :src="require(`@/assets/images/main_visual_swipe${e}.png`)" :alt="`배너`">
      </swiper-slide>
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>
      <div class="swiper-pagination">
      <div class="toggleauto">
        <button @click="toggleAutoplay">
          <img v-if="isAutoplayEnabled" :src="require(`@/assets/images/ic_stop1.png`)" alt="일시정지">
          <img v-else :src="require(`@/assets/images/ic_play1.png`)" alt="시작">
          <!-- <img v-if="isAutoplayEnabled" 
          :style="{'background-image': 'url(' + require(`../assets/images/ic_stop1.png`) + ')'}" alt="일시정지">
          <img v-else 
          :style="{'background-image': 'url(' + require(`../assets/images/ic_play1.png`) + ')'}" alt="시작"> -->
        </button>
      </div>
      </div>
    </swiper>
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
      modules: [Pagination, Navigation, Autoplay],
    };
  },
  data() {
    return {
      isAutoplayEnabled: true,
    }
  },
  methods: {
     toggleAutoplay() {
      this.isAutoplayEnabled = !this.isAutoplayEnabled && { delay: 1000, disableOnInteraction: true }

    },
    onSwiperInit(swiper) {
      // console.log(swiper)
      if (this.isAutoplayEnabled) {
        swiper.autoplay.start()
      } else {
        swiper.autoplay.stop()
      }
    },
  },
  }
</script>

<style lang="scss">
.toggleauto{
  position: absolute;
  bottom: 5px;
  left: 70px;
  z-index: 70;
  background-color: transparent;
  button{
    border: 0;
    outline: 0;
    cursor: pointer;
    background: transparent;
    img{
      position: relative;
      display: inline-block;
      width: 50px;
      height: 36px;
    }
  }
}



.wrap_visual{
  height: 690px;
  position: relative;
  padding-top: 101px;
}
.mySwiper_visual{
  position: relative;
  height: inherit;
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