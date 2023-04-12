<template>
  <header class="header-nav">
    <div class="container">
      <router-link to="/" class="header-nav__logo">
        <icon name="logo" /> coinrule
      </router-link>
      <ul class="header-nav__actions">
        <li>
          <router-link to="#">Pricing</router-link>
        </li>
        <li>
          <router-link to="#">Log In</router-link>
        </li>
        <li>
          <router-link to="#" class="bordered">Get Started</router-link>
        </li>
      </ul>
    </div>
  </header>
</template>

<script>
import Icon from "@/components/atoms/icon/index.vue";

export default {
  name: "HeaderNav",
  components: {Icon}
}
</script>

<style scoped lang="scss">
.header-nav {
  height: 94px;
  .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: inherit;
  }
  a {
    color: #FFF;
    &.bordered {
      padding: 14.5px 30.44px 14.5px 31px;
      border-radius: 100px;
      border: 2px solid #FFFFFF;
    }
  }
  &__logo {
    display: flex;
    align-items: center;
    gap: 25px;
    letter-spacing: 2.24px;
    text-transform: uppercase;
    font-weight: 500;
    font-size: 30px;
    line-height: 30px;
  }
  &__actions {
    li {
      display: inline-block;
      & + li {
        margin-left: 44px;
      }
      a {
        font-weight: 300;
        font-size: 18px;
        line-height: 27px;
        text-transform: capitalize;
      }
    }

  }
}
</style>