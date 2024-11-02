<script setup lang="ts">
import LogoHome from './icons/LogoHome.vue'
import ArrowIcon from './icons/ArrowIcon.vue'
import NumberIcon from './icons/NumberIcon.vue'
import { ref } from 'vue'

const canClick = ref<boolean>(true)

const ClickImg = (): void => {
  if (canClick.value) {
    canClick.value = false
  }
}
</script>

<template>
  <section class="home" :class="{ HomeActive: !canClick }">
    <div class="container">
      <div class="home__content">
        <LogoHome class="home__logo" />

        <div class="home__img" @click="ClickImg">
          <div class="home__click">
            <span>Открой меня</span>
            <ArrowIcon class="home__arrow" />
          </div>
          <img src="/rolton.png" alt="png" />
          <img src="/rolton_open.png" alt="png" />
        </div>
      </div>
    </div>

    <div class="home__text">
      <NumberIcon class="home__number"/>
      <h1>лет дарим тепло</h1>
    </div>

    <div class="home__objects">
      <img
        class="home__objects-img"
        src="/home/onion.png"
        alt="png"
        v-for="i in 2"
        :key="i"
      />
      <img class="home__objects-img" src="/home/carrot.png" alt="png" />
      <img
        class="home__objects-img"
        src="/home/small-spagget.png"
        alt="png"
        v-for="i in 2"
        :key="i"
      />
      <img
        class="home__objects-img"
        src="/home/spagget.png"
        alt="png"
        v-for="i in 4"
        :key="i"
      />
    </div>

    <div class="home__gradient"></div>
    <div class="home__big-gradient"></div>
  </section>
</template>

<style lang="scss" scoped>
@use '@/assets/styles/home.scss';
</style>
