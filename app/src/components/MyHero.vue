<template class="bg-white">
  <Carousel :items="visibleSlides" :autoplay="2000" :wrap-around="true">
    <Slide
      v-for="(slide, index) in visibleSlides"
      :key="index"
      :content="slide"
    >
      <div
        class="carousel__item"
        :style="{ backgroundImage: `url(${slide.src})` }"
      >
        <img :src="slide.src" :alt="slide.alt" class="carousel-image" />
      </div>
    </Slide>
  </Carousel>
</template>

<script lang="ts" setup>
import { ref, computed, onMounted, onBeforeUnmount } from 'vue'
import { Carousel, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

import bgHero1 from '../assets/bg-hero-1.jpg'
import bgHero2 from '../assets/bg-hero-2.jpg'
import bgHero3 from '../assets/bg-hero-3.jpg'
import bgHero4 from '../assets/bg-hero-4.jpg'

const slidesDesktop = ref([
  { src: bgHero1, alt: 'Image 1' },
  { src: bgHero2, alt: 'Image 2' },
])

const slidesMobile = ref([
  { src: bgHero3, alt: 'Image 3' },
  { src: bgHero4, alt: 'Image 4' },
])

const screenWidth = ref(window.innerWidth)

const visibleSlides = computed(() => {
  return screenWidth.value < 768 ? slidesMobile.value : slidesDesktop.value
})

const updateScreenWidth = () => {
  screenWidth.value = window.innerWidth
}

onMounted(() => {
  window.addEventListener('resize', updateScreenWidth)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', updateScreenWidth)
})
</script>

<style scoped>
.carousel {
  display: flex;
  width: 100%;
}

.carousel__item {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  max-height: 70vh;
  overflow: hidden;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.carousel__item img {
  width: 100%;
  height: auto;
  object-fit: cover;
}
</style>
