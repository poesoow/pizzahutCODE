<template>
  <div class="wrap_personal">
    <section>
      <div class="order_area">
        <ul>
          <li>
            <a href="#" @click.prevent>
              <img :src="require(`@/assets/images/ic_delivery.png`)" :alt="`배달주문`">
              <span>배달주문</span>
            </a>
          </li>
          <li>
            <a href="#" @click.prevent>
              <img :src="require(`@/assets/images/ic_packaging.png`)" :alt="`포장주문`">
              <span>포장주문</span>
            </a>
          </li>
          <li>
            <a href="#" @click.prevent>
              <img :src="require(`@/assets/images/ic_favorite.png`)" :alt="`마이오더`">
              <span>마이오더</span>
            </a>
          </li>
        </ul>
      </div>
      <div class="login_area">
        <p class="login_message"><span>로그인</span>하고 더 많은 혜택을 즐겨보세요!</p>
        <div class="login_btnBoxs">
          <div class="login_btnSet">
            <button><span>로그인/회원가입</span></button>
            <button><span>비회원 주문조회</span></button>
          </div>
          <div class="login_btnStamp">
            <button><em>나의 스탬프 </em><span>적립 현황</span></button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    name: 'PersonalArea'
  }
</script>

<style lang="scss" scoped>
  .wrap_personal{
    position: relative;
    height: 370px;
    background-color: #f7f7f7;
    section{
      width: 1440px;
      margin: 0 auto;
      padding: 190px 0 40px;
      position: relative;
      .order_area{
        width: 100%;
        position: absolute;
        top: -100px;
        left: 40px;
        z-index: 60;
        ul{
          display: flex;
          gap: 20px;
          li{
            flex-basis: calc((100% - 140px) / 3);
            background-color: #fff;
            height: 200px;
            border-radius: 20px;
            border: 2px solid #fff;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            a {
              width: inherit;
              height: inherit;
              display: flex;
              align-items: center;
              justify-content: center;
              flex-direction: column;
              font-size: 24px;
            }
          }
        }
      }
      .login_area{
        margin-top: -41px;
        margin-left: 40px;
        .login_message{
          font-weight: 200;
          font-size: 28px;
          position: relative;
          padding-left: 96px;
          span{
            font-weight: bold;
          }
          &::before{
            content: '';
            display: block;
            width: 80px;
            height: 80px;
            position: absolute;
            left: 0;
            top: -50%;
            border-radius: 50%;
            background-color: #fff;
            background-image: url("../assets/images/ic_login.png");
            background-repeat: no-repeat;
            background-position: center;
          }
        }
        .login_btnBoxs{
          margin-top: 48px;
          display: flex;
          justify-content: space-between;
          // button 공통 속성
          button{
            padding: 0 45px;
            height: 80px;
            line-height: 80px;
            background-color: #fff;
            border-radius: 12px;
            border: 1px solid #fff;
            span{
              font-weight: 600;
              font-size: 26px;
              padding-bottom: 2px;
              border-bottom: 1px solid #000;
            }
          }
          .login_btnSet{
            display: flex;
            gap: 10px;
          }
          .login_btnStamp{
            margin-right: 40px;
            em{
              font-size: 26px;
              color: #777;
              margin-right: 17px;
              font-style: normal;
            }
          }
        }
      }
    }
  }
</style>