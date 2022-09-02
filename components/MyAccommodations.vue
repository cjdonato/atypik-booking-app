<template>
  <div>
    <p v-if="$fetchState.pending">Loading....</p>
    <p v-else-if="$fetchState.error">Error</p>
    <div v-else>
      <h1 class="font-bold text-xl">Mes hebergements</h1>
      <NuxtLink
        v-for="accom in accommodations"
        :key="accom.id"
        :to="{ name: 'product-id', params: { id: accom.id } }"
        class="card lg:card-side bg-base-100 shadow-xl mb-8 min-w-full h-32"
      >
        <figure>
          <img :src="accom.image" alt="Album" class="w-48" />
        </figure>
        <div class="card-body p-3 flex flex-row">
          <div>
            <h2 class="card-title">{{ accom.name }}</h2>
            <p class="text-sm truncate w-48">
              {{ accom.description }}
            </p>
          </div>
          <div>
            <p class="text-base w-48">
              Type : {{ accom.type }}
            </p>
            <p class="text-base w-48">
              Prix : {{ accom.price }}
            </p>
            <p class="text-base w-48">
              Capacite : {{ accom.capacity }}
            </p>
          </div>
        </div>
      </NuxtLink>
    </div>
    <NuxtLink class="btn mb-4" :to="{ name: 'product-add' }"
      >Ajouter un hebergement</NuxtLink
    >
  </div>
</template>

<script>
export default {
  name: 'MyAccommodations',
  data: () => ({
    accommodations: [],
  }),
  async fetch() {
    const user = JSON.parse(localStorage.getItem('user'))
    await this.$axios
      .$get('/accommodation/user/' + user.id)
      .then((response) => {
        console.log(response)
        this.accommodations = response
      })
  },
}
</script>
