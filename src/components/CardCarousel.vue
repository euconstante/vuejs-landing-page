<script lang="ts">
import { defineComponent } from 'vue'

import '../assets/styles/components/CardCarousel.css'

export default defineComponent({
  props: {
    images: Array as () => string[],
    slideInterval: Number as () => 3000,
    text: Array as () => string[],
    title: Array as () => string[],
  },
  data() {
    return {
      currentIndex: 0,
    }
  },
  computed: {
    sliderStyle(): string {
      return `transform: translateX(-${this.currentIndex * 100}%); width: ${this.images.length * 100}%;`
    },
  },
  methods: {
    slideToNext() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length
    },
    slideStyle(index: number): string {
      return `width: ${100 / this.images.length}%;`
    },
    goToSlide(index: number) {
      this.currentIndex = index
    },
  },
  watch: {
    currentIndex(newIndex) {
      setTimeout(this.slideToNext, this.slideInterval)
    },
  },
  created() {
    setTimeout(this.slideToNext, this.slideInterval)
  },
})
</script>
<template>
  <div class="card-carousel">
    <div class="card-carousel__container">
      <div class="card-carousel__slider" :style="sliderStyle">
        <div class="card-carousel__slide" v-for="(image, index) in images" :key="index" :style="slideStyle(index)">
          <img :src="image" alt="Carousel Slide" class="card-carousel__image" />
          <h3 class="card-carousel__title hide title--small">{{ title[index] }}</h3>
          <p class="card-carousel__text description--medium">{{ text[index] }}</p>
          <div class="card-carousel__gradient-radial"></div>
        </div>
      </div>
    </div>
    <div class="card-carousel__indicators">
      <div
        class="card-carousel__indicator"
        v-for="(image, index) in images"
        :key="index"
        :class="{ active: index === currentIndex }"
        @click="goToSlide(index)"
      ></div>
    </div>
  </div>
</template>

<style scoped></style>
