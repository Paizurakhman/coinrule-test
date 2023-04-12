<script setup lang="ts">
import { RouterView } from 'vue-router'
import HeaderNav from "@/components/organisms/header/index.vue";
</script>

<template>
  <div>
    <HeaderNav />
    <RouterView />
  </div>
</template>

<style scoped>

</style>
