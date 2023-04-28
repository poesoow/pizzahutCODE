<!-- eslint-disable vue/no-parsing-error -->
<template>
  <div class="wrap">
    <div class="wrap_header">
      <div class="logo">
        <a href="https://www.pizzahut.co.kr/">
          <img :src="require('@/assets/images/logo1.png')" alt="로고">
        </a>
      </div>
      <nav @mouseleave="hovernav = ''" class="gnb">
        <ul class="nav">
          <li @mouseover="hovernav = e" v-for="e in navlist" :key="e"><a href="#" @click.prevent>{{ e }}</a></li>
        </ul>
        <!-- 호버메뉴 영역 -->
        <div class="hoverMenu">
          <ul>
            <li
              v-for="(e, index) in navsublist[this.hovernav]" :key="index">
              {{ e }}
            </li>
          </ul>
        </div>
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
          <!-- menutoggle;  -->
          <a class="hamburger" :class="{ on: menuActive }" @click.prevent="menutoggle" href="#"><span></span></a>
        </div>
      </div>
    </div>
    <!-- 서브메뉴 영역 -->
    <div v-if="menuActive === true" class="wrap_submenu" :style="menuActive === true ? 'overflow-y: scroll': ''">
      <ul class="submenu">
        <li class="menuname" v-for="(list, index) in navMenulist" :key="index">
          <h3>{{ index }}</h3>
          <ul>
            <li v-for="e in list" :key="e">{{ e }}</li>
          </ul>
        </li>
      </ul>
      <div>
        <img :src="require(`@/assets/images/menu_banner.png`)" :alt="`메뉴배너`">
      </div>
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
        navsublist: navdata.Nav.navSubList,
        hovernav: '',
        menuActive: false, // 햄버거 메뉴
        navMenulist: navdata.NavMenu.List,
      }
    },
    methods: {
      menutoggle(){
        if(this.menuActive === false){
          document.querySelector('body').style = 'overflow: hidden;'
          this.menuActive = true
        }else{
          document.querySelector('body').style = 'overflow: visible;'
          this.menuActive = false
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
@import '../style/util.scss';

.wrap{
  position: fixed;
  z-index: 50;
  background: rgba(255, 255, 255, 0.95);
  left: 0;
  right: 0;
  .wrap_header{
    max-width: 1720px;
    height: 101px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    color: #000;
    border-bottom: 1px solid #eee;
    div.logo{
    width: 210px;
    box-sizing: border-box;
    }
    nav.gnb {
      ul.nav{
        display: flex;
        @include tablet{
          display: none;
        }
        @include mobile{
          display: none;
        }
        li{
          flex-shrink: 0;
          position: relative;
          &:hover::after{
            content: '';
            display: block;
            position: absolute;
            width: 100%;
            z-index: 50;
            border-bottom: 1px solid #c8102e;
          }
          a{
            display: block;
            margin: 0 30px;
            padding: 36px 0;
            font-weight: 500;
            font-size: 20px;
          }
        }
      }
      .hoverMenu{
        position: absolute;
        top: 101px;
        left: 0;
        right: 0;
        background-color: #fff;
        border-top: none;
        z-index: 40;
        box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.07);
        ul {
          margin-left: 330px;
          display: flex;
          li{
          height: 64px;
          padding-top: 30px;
          margin-right: 60px;
          &:hover{
            color: #c8102e;
          }
          }
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
        @include desktop{
          display: none;
        }
        @include tablet{
          display: block;
        }
        @include mobile{
          display: block;
        }
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
          @include mobile{
          display: block;
          margin-right: 0;
        }
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
  .wrap_submenu{
    position: relative;
    z-index: 10;
    background: #fff;
    height: calc(100vh - 100px);
    // overflow-y: scroll;
    padding-top: 72px;
    margin-bottom: 50px;
    // left: 409px;
    padding-left: 409px;
    display: flex;
    @include desktop{
      padding-left: 250px;
    }
    @include tablet{
      padding-left: 150px;
      padding-top: 40px;
    }
    @include mobile{
      padding-left: 100px;
      padding-top: 40px;
    }
    ul.submenu{
      width: 720px;
      display: flex;
      flex-wrap: wrap;
      li.menuname{
        flex: 1 1 30%;
        h3{
          font-weight: 600;
          font-size: 22px;
          line-height: 1.3;
          position: relative;
          width: max-content;
        }
        ul li{
          margin-top: 15px;
          position: relative;
          width: max-content;
          &:hover{
            color: #c8102e;
            &::after{
              content: '';
              position: absolute;
              display: block;
              width: 100%;
              border-bottom: 1px solid #c8102e;
            }
          }
        }
        &:nth-of-type(3):hover h3,
        &:nth-of-type(5):hover h3,
        &:nth-of-type(6):hover h3,
        &:nth-of-type(10):hover h3,
        &:nth-of-type(12):hover h3{
          color: #c8102e;
          &::after{
              content: '';
              position: absolute;
              display: block;
              width: 100%;
              border-bottom: 1px solid #c8102e;
            }
        }
      }
    }
    img{
      border-radius: 16px;
      box-shadow: 0 15px 45px 0 rgba(0, 0, 0, 0.2);
      @include tablet{
        display: none;
      }
      @include mobile{
        display: none;
      }
    }
  }
}
</style>