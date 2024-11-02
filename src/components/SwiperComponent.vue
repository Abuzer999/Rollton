<script setup lang="ts">
import { ref } from 'vue'
import Card from './CardComponent.vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import ArrowSwiper from './icons/ArrowSwiper.vue'
import ModalComponent from './ModalComponent.vue'
import 'swiper/css'
import { Navigation } from 'swiper/modules'
import type { State } from '@/types/type'

const modules = [Navigation]
const cards = ref<State[]>([
  {
    id: 1,
    url: './slides/slide1.png',
    beforeUrl: '/slides/line1.png',
    year: '1999',
    text: 'Первая пачка вермишели',
  },
  {
    id: 2,
    url: './slides/slide2.png',
    beforeUrl: '/slides/line2.png',
    year: '2001',
    text: 'Запуск картофельного пюре',
  },
  {
    id: 3,
    url: './slides/slide3.png',
    beforeUrl: '/slides/line3.png',
    year: '2002',
    text: 'Запуск бульонов',
  },
  {
    id: 4,
    url: './slides/slide1.png',
    beforeUrl: '/slides/line1.png',
    year: '2003',
    text: 'Первая пачка вермишели',
  },
  {
    id: 5,
    url: './slides/slide2.png',
    beforeUrl: '/slides/line2.png',
    year: '2004',
    text: 'Запуск картофельного пюре',
  },
  {
    id: 6,
    url: './slides/slide3.png',
    year: '2005',
    text: 'Запуск бульонов',
  },
])

const isModal = ref<boolean>(false)
const selectedCard = ref<State>({
  id: 0,
  url: '',
  beforeUrl: '',
  year: '',
  text: '',
})

const openModal = (card: State): void => {
  selectedCard.value = card
  document.body.style.overflow = 'hidden'
  isModal.value = true
}

const closeModal = (): void => {
  isModal.value = false
  document.body.style.overflow = 'auto'
}
</script>

<template>
  <section class="cards">
    <div class="container">
      <h1>
        <span>История</span>
        <span>Ролтон</span>
      </h1>

      <swiper
        :modules="modules"
        :breakpoints="{
          0: {
            slidesPerView: 1,
            spaceBetween: 80,
          },
          550: {
            slidesPerView: 1,
            spaceBetween: 0,
          },
          750: {
            slidesPerView: 2,
            spaceBetween: 0,
          },
          950: {
            slidesPerView: 2,
            spaceBetween: 10,
          },
          1125: {
            slidesPerView: 3,
            spaceBetween: 20,
          },
          1450: {
            slidesPerView: 3,
            spaceBetween: 70,
          },
          1650: {
            slidesPerView: 3,
            spaceBetween: 240,
          },
        }"
        class="cards__food"
      >
        <SwiperSlide class="cards__slide" v-for="card in cards" :key="card.id">
          <Card
            :id="card.id"
            :url="card.url"
            :before-url="card.beforeUrl"
            :year="card.year"
            :text="card.text"
            @handleHalfClick="openModal(card)"
          />
        </SwiperSlide>

        <div class="cards__btn">
          <button>
            <ArrowSwiper />
          </button>
        </div>
      </swiper>
    </div>
  </section>

  <div
    class="cards__overlay"
    :class="['cards__overlay', { 'modal-active': isModal }]"
  >
    <div class="cards__modal-bg" @click.self="closeModal"></div>
    <ModalComponent
      class="cards__modal"
      :id="selectedCard.id"
      :text="selectedCard.text"
      :year="selectedCard.year"
      :url="selectedCard.url"
      @close="closeModal"
    />
  </div>
</template>

<style lang="scss" scoped>
@use '@/assets/styles/swiper.scss';
</style>
