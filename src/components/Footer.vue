<template>
  <div class="wrap_footer">
    <div class="footer_logo">
      <img :src="require(`@/assets/images/logo2.png`)" alt="로고">
    </div>
    <div class="footer_info">
      <ul>
        <li>이용약관</li>
        <li class="privacy">개인정보처리방침</li>
        <li>공지사항</li>
        <li>창업안내</li>
        <li>대표번호 1588-5588(운영시간 10:30 ~ 22:00)</li>
      </ul>
      <div class="footer_main">
        <p>서울시 영등포구 국회대로 74길 4, 9~11층</p>
        <p><span>사업자등록번호 120-81-63948</span><span>통신판매업신고번호 제2018-서울영등포-1220호</span></p>
        <p><span>한국피자헛유한회사 대표이사 : 김진영</span><span>개인정보 보호책임자 : 김기철</span></p>
      </div>
      <div class="copy">Copyright © BY PIZZA HUT KOREA LTD. ALL RIGHT RESERVED</div>
    </div>
    <div class="footer_ranking">
      <p>한국능률협회 컨설팅 23년 연속(2001~ 2023) 선정</p>
      <p>한국 산업의 브랜드파워 피자전문점 부문 1위 피자헛</p>
    </div>
    <div class="footer_sns">
      <img :src="require(`@/assets/images/ic_share_facebook1.png`)" alt="페이스북">
      <img :src="require(`@/assets/images/ic_share_instagram1.png`)" alt="인스타그램">
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
    height: 200px;
    background-color: #444;
    margin: 0 auto;
    padding: 45px 100px 0 100px;
    overflow: hidden;
    .footer_logo{
      width: 300px;
      display: inline-block;
      vertical-align: top;
    }
    .footer_info{
      display: inline-block;
      font-weight: 200;
      font-size: 18px;
      color: #aaa;
      ul {
        margin-bottom: 25px;
        li{
          display: inline-block;
          &:not(:last-child)::after{
            content: '';
            display: inline-block;
            width: 1px;
            height: 13px;
            background-color: #777;
            margin: 0 25px 2px 30px;
            vertical-align: middle;
          }
        }
        li.privacy{
          color: #fff;
        }
      }
      .footer_main{
        font-size: 15px;
        line-height: 1.71;
        margin-bottom: 33px;
        p span:first-child::after{
          content: '';
          display: inline-block;
          width: 1px;
          height: 13px;
          background-color: #aaa;
          margin: 0 10px 2px 13px;
          vertical-align: middle;
        }
      }
      .copy{
        font-weight: 100;
        font-size: 13px;
        color: #aaa;
      }
    }
    .footer_ranking{
      float: right;
      vertical-align: top;
      margin-top: 88px;
      font-weight: 200;
      font-size: 13px;
      color: #aaa;
      height: 50px;
      line-height: 26px;
      letter-spacing: 0;
      padding-left: 70px;
      background: url(@/assets/images/ic_kbpi.png) no-repeat left center;
    }
    .footer_sns{
      position: absolute;
      top: 45px;
      right: 100px;
      img:not(:last-child){
        margin-right: 32px;
      }
    }
  }

</style>