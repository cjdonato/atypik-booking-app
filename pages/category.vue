<template>
  <CustomTemplate>
    <Search />

    <p v-if="$fetchState.pending">Loading....</p>
    <p v-else-if="$fetchState.error">Error</p>
    <NuxtLink
      v-else
      :to="{ name: 'product-id', params: { id: accommodations[0].id } }"
      class="card lg:card-side bg-base-100 shadow-xl mb-8 min-w-full"
    >
      <figure>
        <img :src="accommodations[0].image" alt="Album" width="300" height="300"/>
      </figure>
      <div class="card-body">
        <h2 class="card-title">{{ accommodations[0].name }}</h2>
        <p class="text-justify">
          {{ accommodations[0].description }}
        </p>
      </div>
    </NuxtLink>

    <div class="grid grid-cols-2 gap-4">
      <NuxtLink
        v-for="accom in accommodations.slice(1, 5)"
        :key="accom.id"
        :to="{ name: 'product-id', params: { id: accom.id } }"
        class="card w-96 bg-base-100 shadow-xl"
      >
        <figure>
          <img :src="accom.image" alt="Shoes" />
        </figure>
        <div class="card-body">
          <h2 class="card-title">{{ accom.name }}</h2>
        </div>
      </NuxtLink>
      <button class="btn col-span-full">Voir tout</button>
    </div>

    <Newsletter />
  </CustomTemplate>
</template>

<script>
import CustomTemplate from '~/components/CustomTemplate.vue'
import Newsletter from '~/components/Newsletter.vue'
import Search from '~/components/Search.vue'

export default {
  name: 'CategoryPage',
  components: { CustomTemplate, Newsletter, Search },
  data: () => ({
    accommodations: [],
  }),
  async fetch() {
    await this.$axios.$get('/accommodation/').then((response) => {
      // console.log(response)
      this.accommodations = response
    })
  },
}
</script>
