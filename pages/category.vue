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
    <div class="grid grid-cols-2 gap-4">
      <div v-for="n in 4" :key="n" class="card w-96 bg-base-100 shadow-xl">
        <figure>
          <img src="https://placeimg.com/400/225/arch" alt="Shoes" />
        </figure>
        <div class="card-body">
          <h2 class="card-title">Bulle {{ n }}</h2>
        </div>
      </div>
    <button class="btn col-span-full">Voir tout</button>
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
  name: 'CategoryPage',
  components: { CustomTemplate, Newsletter, Search },
})
</script>
