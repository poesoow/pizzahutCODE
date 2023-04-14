<!-- eslint-disable vue/no-parsing-error -->
<template>
  <div class="wrap_header">
    <div class="logo">
      <a href="https://www.pizzahut.co.kr/">
        <img :src="require('@/assets/images/logo1.png')" alt="로고">
      </a>
    </div>
    <nav class="gnb">
      <ul>
        <li v-for="e in navlist" :key="e"><a href="#"  @click.prevent>{{ e }}</a></li>
      </ul>
    </nav>
    <div class="utility">
      <div class="gps">
        <button>
          <span>주소를 입력해 주세요.</span>
        </button>
      </div>
      <div class="icons">
        <a @click.prevent href="#"><img :src="require('@/assets/images/ic_util_my.png')" alt="마이페이지" title="마이페이지"></a>
        <a class="cart" @click.prevent href="#"><img :src="require('@/assets/images/ic_util_cart.png')" alt="장바구니" title="장바구니"><span class="count">0</span></a>
        <a class="hamburger" :class="{ on: menuActive }" @click.prevent="menuActive = menuActive ? false : true" href="#"><span></span></a>
      </div>
    </div>
    <!-- 서브메뉴 영역 -->
    <div>

    </div>
</div>
</template>

<script>
  import navdata from '@/assets/Data.json'

  export default {
    name: 'HeaderView',
    data() {
      return {
        navlist: navdata.Nav.navList,
        menuActive: false, // 햄버거 메뉴
      }
    },
  }
</script>

<style lang="scss" scoped>
.wrap_header{
  max-width: 1720px;
  height: 101px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  color: #000;
  div.logo{
  width: 210px;
  box-sizing: border-box;
  }
  nav.gnb ul{
    display: flex;
    li{
      flex-shrink: 0;
      a{
        display: block;
        margin: 0 30px;
        padding: 30px 0;
        font-weight: 500;
        font-size: 20px;
      }
    } 
  }
  div.utility{
    flex-grow: 1;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    gap: 30px;
    .gps{
      text-align: right;
      button{
        font-weight: 400;
        font-size: 18px;
        color: #000;
        background: none;
        border: 0;
        outline: none;
        cursor: pointer;
        margin-right: 64px;
        position: relative;
        &::before{
          content: '';
          display: block;
          background: url(../assets/images/ic_marker3.png) no-repeat;
          width: 25px;
          height: 28px;
          position: absolute;
          left: -30px;
          top: 0;
          bottom: 0;
        }
        &::after{
          content: '';
          display: block;
          width: 7px;
          height: 9px;
          background: url(../assets/images/ic_arrow1.png) no-repeat center;
          position: absolute;
          right: -18px;
          top: 10px;
        }
      }
    }
    .icons{
      display: flex;
      align-items: center;
      gap: 30px;
      a.cart{
        position: relative;
        span.count{
          position: absolute;
          left: 15px;
          top: -9px;
          width: 23px;
          height: 23px;
          line-height: 23px;
          font-weight: 400;
          font-size: 14px;
          color: #fff;
          text-align: center;
          background-color: #da1a32;
          border-radius: 20px;
          text-indent: 0px !important;
      }
      } 
      a.hamburger{
        position: relative;
        display: block;
        width: 28px;
        height: 4px;
        &::after, &::before{
          content: '';
          position: absolute;
          display: block;
          // require로 준것이 아니라서 빌드한 경우 잘 동작하는지 확인 필요
          background: url(../assets/images/ic_util_menubar.png) no-repeat;
          height: 3px;
          width: 28px;
          right: 0;
          top: 0;
          transition: 0.3s;
        }
        &::after{
          top: -5px;
        }
        &::before{
          top: 5px;
        }
        &.on::after{
          transform: rotate(45deg);
          top: 1px;
        }
        &.on::before{
          transform: rotate(-45deg);
          top: 0px;
        }
      } 
    }
  }
}

</style>