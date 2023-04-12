<template>
  <Header />
  <MainFirst />
</template>

<script>
import Header from './components/Header.vue';
import MainFirst from './components/MainFirst.vue';


export default {
  name: 'App',
  components: {
    Header,
    MainFirst
}
}
</script>

<style lang="scss">
  @charset "uft-8";
  *{margin: 0; padding: 0; font-family: 'Noto Sans KR';}
  ul{list-style: none;}
  a{text-decoration: none; color: #000;}
  img{vertical-align: middle;}
  
</style>
