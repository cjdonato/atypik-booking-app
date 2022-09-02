<template>
  <CustomTemplate>
    <Search />
    <Carousel />
    <div class="carousel carousel-center max-w-full p-4 space-x-4 rounded-box">
      <div v-for="n in 5" :key="n" class="carousel-item">
        <HomeCard />
      </div>
    </div>
    <Newsletter />
  </CustomTemplate>
</template>

<script>
import Search from '../components/Search.vue'
import Carousel from '../components/Carousel.vue'
import Newsletter from '~/components/Newsletter.vue'
import CustomTemplate from '~/components/CustomTemplate.vue'
import HomeCard from '~/components/HomeCard.vue'

export default {
  name: 'IndexPage',
  components: { Search, Carousel, Newsletter, CustomTemplate, HomeCard },
  data: () => ({
    accommodations: [],
  }),
  async fetch() {
    await this.$axios.$get('/accommodation/').then((response) => {
      console.log(response)
      this.accommodations = response
    })
  },
}
</script>
