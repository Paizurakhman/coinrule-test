<template>
  <header class="header-nav container">
      <div class="header-nav__content">
        <router-link to="/" class="header-nav__logo">
          <icon name="logo" />
          <span>coinrule</span>
        </router-link>
        <div class="header-nav__actions">
          <router-link to="#" >Pricing</router-link>
          <router-link to="#" >Log In</router-link>
          <router-link to="#" >Get Started</router-link>
        </div>
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
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  height: 94px;
  &__content {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  a {
    color: #FFF;
  }
  &__logo {
    display: flex;
    align-items: center;
    gap: 25px;
    span {
      letter-spacing: 2.24px;
      text-transform: uppercase;
      font-weight: 500;
      font-size: 30px;
      line-height: 30px;
      padding-top: 8px;
    }
  }
  &__actions {
    a {
      font-weight: 300;
      font-size: 18px;
      line-height: 27px;
      text-transform: capitalize;
      & + a {
        margin-left: 44px;
      }
    }
  }
}
</style>