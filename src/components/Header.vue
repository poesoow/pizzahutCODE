<!-- eslint-disable vue/no-parsing-error -->
<template>
  <div class="wrap_header">
    <div class="logo">
      <a href="#" @click.prevent>
        <img :src="require('@/assets/images/logo1.png')" alt="로고">
      </a>
    </div>
    <nav class="gnb">
      <ul>
        <li v-for="e in navlist" :key="e"><a href="#">{{ e }}</a></li>
      </ul>
    </nav>
    <div class="utility">
      <div class="gps">
        <input type="text" placeholder="주소를 입력해 주세요.">
      </div>
      <div class="icons">
        <a href="#"><img :src="require('@/assets/images/ic_util_my.png')" alt="마이페이지" title="마이페이지"></a>
        <a href="#"><img :src="require('@/assets/images/ic_util_cart.png')" alt="장바구니" title="장바구니"></a>
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
        navlist: navdata.Nav.navList
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
  .logo{
    width: 210px;
    box-sizing: border-box;
  }
  div{
    background-color: #fff;
  }
  nav ul{
    display: flex;
    li a{
      padding: 30px;
      font-weight: 400;
      font-size: 20px;
    }
  }
}

</style>