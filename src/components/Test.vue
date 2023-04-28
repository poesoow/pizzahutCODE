<template>
  <div class="SassComponent">
    dddddd
    <div class="box red"></div>
    <div class="box"></div>
  </div>
</template>

<script>
  export default {
    name: "TestView"
  }
</script>

<style lang="scss" scoped>

@import '../style/util.scss';/*변수파일 import*/

/*반응형 mixin으로 깔끔하게 사용하기*/
.SassComponent{
  display:flex;

  @include mobile{
  /*브라우저 사이즈767px이하일때*/
    background: pink;
  }
  @include tablet{
  /*브라우저 사이즈1023px이하일때*/
    background: blanchedalmond;
  }
  @include desktop{
  /*브라우저 사이즈1024px이상일때*/
    background: gray;
  }
  @include desktop1400{
  /*브라우저 사이즈1024px이상일때*/
    background: blue;
  }
  .box{
    cursor: pointer;
    transition: all 0.3s ease-in;

    &.red{
      background: $red; /*변수파일에 있는 red변수 사용*/
      @include square(5);
      /* 5를 넣으므로 넓이, 높이를 mixin suqare에서 계산해줌 */
    }

  }
}

</style>