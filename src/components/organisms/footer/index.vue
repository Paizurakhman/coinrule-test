<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__navigation">
        <ul>
          <li><a href="#">Forgot password?</a></li>
          <li><a href="#">Create account</a></li>
        </ul>
        <ul>
          <li><a href="#">Contact us</a></li>
          <li><a href="#">Terms</a></li>
          <li><a href="#">Policy</a></li>
        </ul>
      </div>
      <div class="footer__top">
        <p>Please check that you are visiting the correct URL</p>
        <base-button
            class="btn"
            prepend-icon="lock"
        >
          <span>https://</span>web.coinrule.com
        </base-button>
      </div>
      <div class="footer__bottom">
        <p class="copyright">© Coinrule Ltd 2023 All rights reserved</p>
        <p class="version">v2.0.18</p>
      </div>
    </div>
  </footer>
</template>

<script>
import BaseButton from "@/components/atoms/base-button/index.vue";

export default {
  name: "CFooter",
  components: {BaseButton}
}
</script>

<style scoped lang="scss">

.footer {
  .container {
    max-width: 550px;
    text-align: center;
    @media screen and (min-width: 768px){
      padding: 0;
    }
    & > div {
      margin-bottom: 80px;

      & + div {
        margin-bottom: 50px;
      }
    }

    p {
      color: #FFFFFF;
      opacity: 0.5;
      line-height: 20px;
    }

    .btn {
      span {
        color: #33AA28;
      }
    }
  }
  &__navigation {
    display: flex;
    justify-content: space-between;
    align-items: center;
    li {
      display: inline-block;
      & + li {
        margin-left: 24px;
      }
      a {
        font-weight: 500;
        font-size: 15px;
        line-height: 20px;

        color: #FFFFFF;
      }
    }
  }
  &__top {
    p {
      margin-bottom: 10px;
      font-weight: 500;
      font-size: 15px;
      line-height: 20px;
    }
  }
  &__bottom {
    .copyright {
      font-weight: 400;
      font-size: 14px;
    }
    .version {
      font-weight: 300;
      font-size: 12px;
    }
  }

  @media screen and (max-width: 767px){
    &__navigation {
      flex-direction: column;
      margin-bottom: 20px !important;
    }
    .container {
      max-width: 100%;
    }
  }
}

</style>