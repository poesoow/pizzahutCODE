<template>
  <div class="wrap_banner">
    <section>
      <div class="banner_info">
        <h3>회원가입 혜택 알아보기</h3>
        <p>회원가입 즉시 100% 쿠폰 지급</p>
        <a href="#" @click.prevent>자세히보기</a>
      </div>
      <div class="banner_main">
        <swiper
        :loop="true"
        :autoplay="{ delay: 5000, }" 
        :modules="modules"
        class="mySwiper_banner"
      >
        <swiper-slide v-for="e in 4" :key="e">
          <div :style="{ 'background-image': 'url(' + require(`@/assets/images/swiper_slide${e}.png`) + ')' }"></div>
        </swiper-slide>
      </swiper>
      </div>
      <div class="banner_thumnail">
        <swiper
        :direction="'vertical'"
        :slidesPerView="3"
        :spaceBetween="25"
        :loop="true"
        :pagination="true"
        :navigation="{ prevEl: '.swiper-button-prev', nextEl: '.swiper-button-next' }"
        :autoplay="{ delay: 1000 }" 
        :modules="modules"
        class="mySwiper_visual"
      >
        <swiper-slide v-for="e in 8" :key="e">
          <!-- <div :style="{ 'background-image': 'url(' + require(`@/assets/images/swiper_slide${e}.png`) + ')' }"></div> -->
          <img :src="require(`@/assets/images/swiper_slide${e}.png`)" :alt="`배너`">
        </swiper-slide>
        <!-- <div class="swiper-button-prev"></div>
        <div class="swiper-button-next"></div> -->
        <div class="swiper-pagination-vertical"></div>
      </swiper>
      </div>
    </section>
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
    name: 'BannerView',
    components: {
      Swiper, SwiperSlide
    },
    setup() {
      return {
        modules: [Pagination, Navigation, Autoplay]
      }
    }
  }
</script>

<style lang="scss">
  .wrap_banner{
    margin: 100px 0 120px;
    // height: 706px;
    section{
      width: 1360px;
      margin: 0 auto;
      padding: 0 40px;
      position: relative;
      display: flex;
      align-items: flex-start;
      .banner_info{
        flex-basis: 216px;
        word-break: keep-all;
        h3{
          font-weight: 600;
          font-size: 28px;
        }
        p{
          font-weight: 200;
          font-size: 22px;
          margin: 15px 0 48px;
        }
        a{
          padding-right: 13px;
          display: inline-block;
          position: relative;
          font-size: 16px;
          &::after{
            content: '';
            display: block;
            position: absolute;
            width: 7px;
            height: 12px;
            right: 0;
            top: 7px;
            background: url(../assets/images/ic_arrow6.png);
          }
        }
      }
      .banner_main{
        flex-basis: 764px;
        height: 100%;
        margin: 0 40px 0 60px;
        .mySwiper_banner{
          position: relative;
          width: 764px;
          /* 아래는 swiper 가지고 온 그대로 */
          .swiper {
            width: 100%;
            height: 100%;
          }
          .swiper-slide {
            text-align: center;
            font-size: 18px;
            /* Center slide text vertically */
            display: flex;
            justify-content: center;
            align-items: center;
          }
          div{
            width: 764px;
            height: 486px;
            background-repeat: no-repeat;
            object-fit: cover;
          }
          .swiper-slide img {
            display: block;
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
          
        }
      }
      .banner_thumnail{
        flex-basis: 280px;
        height: 486px;
        /* 아래는 swiper 가지고 온 그대로 */
          .swiper {
            height: 100%;
            padding-right: 50px;
            position: relative;
          }
          .swiper-slide {
            text-align: center;
            font-size: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
          }
          div{
            background-repeat: no-repeat;
            object-fit: cover;
          }
          .swiper-slide img {
            border-radius: 10px;
            display: block;
            width: 100%;
            height: 100%;
            object-fit: cover;
          }
          
      }
    }
  }
</style>

<style>

.banner_thumnail .swiper-pagination{
  position: absolute;
  background-color: transparent;
  left: 250px;
  right: 0;
  top: 105px;
  font-size: 20px;
}

</style>