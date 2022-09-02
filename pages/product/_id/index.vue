<template>
  <CustomTemplate>
    <Search />

    <p v-if="$fetchState.pending">Loading....</p>
    <div v-else class="card lg:card-side bg-base-100 shadow-xl mb-8 min-w-full">
      <figure>
        <img src="https://placeimg.com/400/400/arch" alt="Album" />
      </figure>
      <div class="card-body">
        <h2 class="card-title">{{ accommodation.name }}</h2>
        <p class="text-justify">
          {{ accommodation.description }}
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

<script>
import CustomTemplate from '~/components/CustomTemplate.vue'
import Newsletter from '~/components/Newsletter.vue'
import Search from '~/components/Search.vue'

export default {
  name: 'ProductPage',
  components: { CustomTemplate, Newsletter, Search },
  data: () => ({
    accommodation: null,
  }),
  async fetch() {
    await this.$axios
      .$get('/accommodation/' + this.$route.params.id)
      .then((response) => {
        // console.log(response)
        this.accommodation = response
      })
  },
}
</script>
