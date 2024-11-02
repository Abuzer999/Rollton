<template>
  <div class="modal">
    <div class="modal__content">
      <ExitIcon class="modal__exit" @click="emit('close')" />
      <div class="modal__left">
        <div class="modal__top">
          <h2>{{ year }}</h2>
          <span>{{ text }}</span>
        </div>

        <div class="modal__bottom">
          <div class="modal__text">
            <p>
              «Роллтон» – это любимые продукты миллионов потребителей.
              А всё потому, что вкус и качество ароматной кудрявой лапши
              и неповторимого нежного пюре остаются неизменными на протяжении
              более, чем 20 лет.
            </p>

            <p>
              «Роллтон» объединяет всех, независимо от пола и возраста, и всегда
              выручает горячим обедом! Где бы вас не настиг голод: на работе,
              в поездке или дома, ваш сытный перекус — всегда под рукой.
            </p>
          </div>
          <img src="/slides/modalImg.png" alt="png" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import type { State } from '@/types/type'
import ExitIcon from './icons/ExitIcon.vue'

const emit = defineEmits<{
  (e: 'close'): void
}>()

defineProps<State>()
</script>

<style lang="scss" scoped>
@use '@/assets/styles/modal.scss';
</style>
