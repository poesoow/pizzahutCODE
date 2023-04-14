<template>
  <div class="wrap_footer">
    <div class="footer_logo">
      <img :src="require(`@/assets/images/logo2.png`)" alt="로고">
    </div>
  </div>
</template>

<script>
  export default {
    name: 'FooterView'
  }
</script>

<style lang="scss" scoped>
  .wrap_footer{
    position: relative;
    width: 1920px;
    height: 240px;
    background-color: #444;
    margin: 0 auto;
    padding: 45px 100px 0 100px;
  }

</style>