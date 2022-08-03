<template>
  <!-- <div class="flex justify-center w-screen bg-green-900"> -->
  <div class="flex justify-center w-screen">
    <div class="carousel w-8/12">
      <div id="slide1" class="carousel-item relative w-full">
        <NuxtImg preset="carousel" src="https://placeimg.com/850/325/arch" placeholder />
        <div
          class="absolute flex justify-between transform -translate-y-1/2 left-5 right-5 top-1/2"
        >
          <a href="#slide4" class="btn btn-circle">❮</a>
          <a href="#slide2" class="btn btn-circle">❯</a>
        </div>
      </div>
      <div id="slide2" class="carousel-item relative w-full">
        <NuxtImg preset="carousel" src="https://placeimg.com/850/325/nature" placeholder />
        <div
          class="absolute flex justify-between transform -translate-y-1/2 left-5 right-5 top-1/2"
        >
          <a href="#slide1" class="btn btn-circle">❮</a>
          <a href="#slide3" class="btn btn-circle">❯</a>
        </div>
      </div>
      <div id="slide3" class="carousel-item relative w-full">
        <NuxtImg preset="carousel" src="https://placeimg.com/850/325/arch" placeholder />
        <div
          class="absolute flex justify-between transform -translate-y-1/2 left-5 right-5 top-1/2"
        >
          <a href="#slide2" class="btn btn-circle">❮</a>
          <a href="#slide4" class="btn btn-circle">❯</a>
        </div>
      </div>
      <div id="slide4" class="carousel-item relative w-full">
        <NuxtImg preset="carousel" src="https://placeimg.com/850/325/nature" placeholder />
        <div
          class="absolute flex justify-between transform -translate-y-1/2 left-5 right-5 top-1/2"
        >
          <a href="#slide3" class="btn btn-circle">❮</a>
          <a href="#slide1" class="btn btn-circle">❯</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'CarouselComponent',
})
</script>
