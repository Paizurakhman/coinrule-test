<script setup lang="ts">
import { RouterView } from 'vue-router'
import HeaderNav from "@/components/organisms/header/index.vue";
import CFooter from "@/components/organisms/footer/index.vue";
</script>

<template>
  <div class="app">
    <HeaderNav />
    <main class="main-content">
      <RouterView />
    </main>
    <CFooter />
  </div>
</template>

<style scoped lang="scss">
.app {
  display: grid;
  grid-template-rows: auto 1fr auto;
  min-height: 100vh;
  .main-content {
    flex: 1;
  }
}
</style>
