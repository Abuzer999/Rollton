<script setup lang="ts">
import RewardIcon from './icons/RewardIcon.vue'
</script>

<template>
  <section class="rewards">
    <div class="container">
      <div class="rewards__content">
        <div class="rewards__text">
          <h1>получили 20 наград</h1>
          <span>в различных номинациях</span>
        </div>

        <RewardIcon />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.rewards {
  position: relative;
  z-index: 2;
  background: #fbd927;

  &__content {
    display: flex;
    align-items: center;

    @media (max-width: 950px) {
      padding-top: 60px;
      flex-direction: column;
      text-align: center;
    }
  }

  &__text {
    display: flex;
    flex-direction: column;
    gap: 20px;
    max-width: 580px;
    width: 100%;

    h1 {
      font-weight: 700;
      font-size: clamp(2.813rem, calc(2.152rem + 3.3vw), 5rem);
      line-height: 110%;
      text-transform: uppercase;
      color: #57a03c;
    }

    span {
      font-weight: 500;
      font-size: clamp(1.25rem, calc(1.08rem + 0.85vw), 1.813rem);
      line-height: 110%;
      color: #000;
    }
  }

  &__main {
    position: relative;
    width: 900px;
    height: 700px;
    background: url('../../public/adward.png');
  }

  &__border {
    position: relative;
    overflow: hidden;
    top: 62px;
    left: 208px;
    width: 556px;
    height: 600px;
    background: url('../../public/adward-border.png');
  }
}
</style>
