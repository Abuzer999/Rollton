<script setup lang="ts">
import WorldIcon from './icons/WorldIcon.vue'
</script>

<template>
  <section class="world">
    <div class="container">
      <div class="world__content">
        <div class="world__text">
          <h1>Теплые моменты с Роллтон</h1>
          <h2>Продали 2 млн км лапши</h2>
          <span>что равно 50-ти обхватам Земли</span>
        </div>

        <WorldIcon />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.world {
  position: relative;
  z-index: 2;
  background: #fbd927;

  &__content {
    display: flex;
    justify-content: space-between;
    padding: clamp(3.75rem, calc(2.052rem + 8.49vw), 9.375rem) 0 30px 0;

    @media(max-width: 950px) {
      padding-bottom: clamp(3.75rem, calc(2.052rem + 8.49vw), 9.375rem);
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
  }

  &__text {
    min-width: clamp(18.125rem, calc(13.031rem + 25.47vw), 35rem);
    display: flex;
    flex-direction: column;
    gap: 20px;

    @media(max-width: 950px) {
      align-items: center;
    }

    h1 {
      max-width: clamp(18.75rem, calc(13.844rem + 24.53vw), 35rem);
      width: 100%;
      font-weight: 700;
      font-size: clamp(1.625rem, calc(1.172rem + 2.26vw), 3.125rem);
      line-height: 110%;
      text-transform: uppercase;
      color: #df231d;
    }

    h2 {
      max-width: clamp(18.125rem, calc(14.163rem + 19.81vw), 31.25rem);
      width: 100%;
      font-weight: 700;
      font-size: clamp(2.813rem, calc(2.152rem + 3.3vw), 5rem);
      line-height: 110%;
      text-transform: uppercase;
      color: #57a03c;
      margin-top: clamp(1.25rem, calc(-0.071rem + 6.6vw), 5.625rem);
    }

    span {
      max-width: clamp(12.5rem, calc(8.726rem + 18.87vw), 25rem);
      width: 100%;
      font-weight: 500;
      font-size: clamp(1.25rem, calc(1.08rem + 0.85vw), 1.813rem);
      line-height: 110%;
      color: #000;
    }
  }
}
</style>
