<script setup lang="ts">
import FooterLogo from './icons/FooterLogo.vue'
</script>

<template>
  <footer class="footer">
    <p>© 2023, Mareven. Все права защищены</p>

    <p>Сделано в <FooterLogo /></p>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  position: relative;
  background: #FFF;
  z-index: 2;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 19px clamp(1.563rem, calc(0.94rem + 3.11vw), 3.625rem);

  p {
    display: flex;
    align-items: baseline;
    gap: 7px;
    font-weight: 400;
    font-size: clamp(0.688rem, calc(0.593rem + 0.47vw), 1rem);
    line-height: 130%;
    color: #ca9161;
  }

  @media (max-width: 650px) {
    flex-direction: column;
    gap: 10px;
  }
}
</style>
