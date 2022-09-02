<template>
  <div>
    <!-- <p v-if="$fetchState.pending">Loading....</p>
    <p v-else-if="$fetchState.error">Error</p>
    <div v-else> -->
    <div>
      <h1>Mes reservations</h1>
      <!-- <NuxtLink
        v-for="accom in accommodations.slice(1, 5)"
        :key="accom.id"
        :to="{ name: 'product-id', params: { id: accom.id } }"
        class="card lg:card-side bg-base-100 shadow-xl mb-8 min-w-full h-32"
      >
        <figure>
          <img
            src="https://placeimg.com/400/400/arch"
            alt="Album"
            class="w-48"
          />
        </figure>
        <div class="card-body">
          <h2 class="card-title">{{ accom.name }}</h2>
          <p class="text-justify">
            {{ accom.description }}
          </p>
        </div>
      </NuxtLink> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyReservations',
  data: () => ({
    accommodations: [],
  }),
  // TODO in backend
  // async fetch() {
  //   await this.$axios.$get('/reservation/').then((response) => {
  //     console.log(response)
  //     this.accommodations = response
  //   })
  // },
}
</script>
