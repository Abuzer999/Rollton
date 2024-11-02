<script setup lang="ts">
import { RouterView } from 'vue-router'
import Footer from './components/FooterComponent.vue'
</script>

<template>
  <div class="wrapper">
    <main>
      <RouterView />
    </main>

    <Footer />
  </div>
</template>

<style scoped lang="scss">

</style>
