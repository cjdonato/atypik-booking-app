<template>
  <CustomTemplate>
    <Search />
    <div class="card lg:card-side bg-base-100 shadow-xl mb-8">
      <figure>
        <img src="https://placeimg.com/400/400/arch" alt="Album" />
      </figure>
      <div class="card-body">
        <h2 class="card-title">Bulle au clair de lune</h2>
        <p class="text-justify">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus
          ultricies, leo nec rutrum tristique, turpis mauris volutpat orci, et
          egestas enim ipsum vel nisi. Curabitur quis nulla id erat lobortis
          elementum vitae ut justo. Vivamus tincidunt arcu neque, sed feugiat
          sem scelerisque at. Sed quis lectus vitae orci condimentum aliquam vel
          eget ex. Mauris bibendum orci vestibulum mi vulputate aliquam. Mauris
          aliquam est dictum lorem consectetur sollicitudin. Nunc in tortor
          lobortis, tincidunt ipsum ut, dignissim dui.
        </p>
      </div>
    </div>

    <div class="flex">
      <img src="https://placeimg.com/400/400/arch" alt="Album" />
      <div class="carousel carousel-center max-w-sm p-4 space-x-4 rounded-box">
        <div v-for="n in 5" :key="n" class="hero bg-base-200 carousel-item">
          <div class="hero-content text-center">
            <div class="max-w-md">
              <h1 class="text-5xl font-bold">Commentaire {{ n }}</h1>
              <p class="py-6">
                Provident cupiditate voluptatem et in. Quaerat fugiat ut
                assumenda excepturi exercitationem quasi. In deleniti eaque aut
                repudiandae et a id nisi.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <Newsletter />
  </CustomTemplate>
</template>

<script lang="ts">
import Vue from 'vue'
import CustomTemplate from '~/components/CustomTemplate.vue'
import Newsletter from '~/components/Newsletter.vue'
import Search from '~/components/Search.vue'

export default Vue.extend({
  name: 'ProductPage',
  components: { CustomTemplate, Newsletter, Search },
})
</script>
