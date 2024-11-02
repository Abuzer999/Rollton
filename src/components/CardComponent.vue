<script setup lang="ts">
import type { State } from '@/types/type'
defineProps<State>()

const emit = defineEmits<{
  (e: 'handleHalfClick'): void
}>()

function handleHalfClick() {
  emit('handleHalfClick')
}
</script>

<template>
  <div class="card" :style="{ '--before-url': `url(${beforeUrl})` }">
    <div class="card__figure" @click="handleHalfClick">
      <img class="card__img" :src="url" alt="png" />
      <div class="card__half"></div>
      <div class="card__blur"></div>
      <div class="card__blur-border"></div>
    </div>
    <h2>{{ year }}</h2>
    <p>{{ text }}</p>
  </div>
</template>

<style lang="scss" scoped>
@use '@/assets/styles/card.scss';
</style>
