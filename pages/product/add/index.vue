<template>
  <CustomTemplate>
    <p class="mb-8">Ajout d'hebergement</p>

    <div id="add-accom-form" class="flex flex-col gap-4 w-128">
      <input
        v-model="type"
        type="text"
        placeholder="Type"
        class="input input-bordered w-full"
      /><input
        v-model="name"
        type="text"
        placeholder="Nom"
        class="input input-bordered w-full"
      />
      <input
        v-model="price"
        type="text"
        placeholder="Prix"
        class="input input-bordered w-full"
      /><input
        v-model="capacity"
        type="text"
        placeholder="Capacite"
        class="input input-bordered w-full"
      />

      <textarea
        v-model="description"
        class="textarea textarea-bordered"
        placeholder="Description"
      ></textarea>
      <button class="btn" @click="add_accommodation">Envoyer</button>
    </div>
  </CustomTemplate>
</template>

<script>
import CustomTemplate from '~/components/CustomTemplate.vue'

export default {
  name: 'AddAccommodationPage',
  components: { CustomTemplate },
  data: () => ({
    type: '',
    name: '',
    price: '',
    capacity: '',
    description: '',
    errored: false,
  }),
  methods: {
    async add_accommodation() {
      await this.$axios
        .$post('/accommodation/add', {
          name: this.name,
          description: this.description,
          image: 'https://placeimg.com/400/400/arch',
          userID: this.$store.state.auth.id,
        })
        .then((response) => {
          console.log(response)
          this.errored = false
          this.$router.push({
            name: 'account',
          })
        })
        .catch((error) => {
          console.log(error)
          this.errored = true
        })
    },
  },
}
</script>
