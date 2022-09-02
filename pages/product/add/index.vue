<template>
  <CustomTemplate>
    <p class="mb-8">Ajout d'hebergement</p>

    <form
      id="add-accom-form"
      class="flex flex-col gap-4 w-128"
      @submit="add_accommodation"
    >
      <select v-model="type" class="select select-bordered w-full" required>
        <option selected>Category 1</option>
        <option>Category 2</option>
        <option>Category 3</option>
      </select>
      <input
        v-model="name"
        type="text"
        placeholder="Nom"
        class="input input-bordered w-full"
        required
      />
      <input
        v-model="price"
        type="number"
        placeholder="Prix"
        class="input input-bordered w-full"
        required
      /><input
        v-model="capacity"
        type="number"
        placeholder="Capacite"
        class="input input-bordered w-full"
        required
      />

      <textarea
        v-model="description"
        class="textarea textarea-bordered"
        placeholder="Description"
        required
      ></textarea>
      <button class="btn" type="submit">Ajouter</button>
    </form>
  </CustomTemplate>
</template>

<script>
import CustomTemplate from '~/components/CustomTemplate.vue'

export default {
  name: 'AddAccommodationPage',
  components: { CustomTemplate },
  data: () => ({
    type: 'Category 1',
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
          type: this.type,
          name: this.name,
          description: this.description,
          price: this.price,
          capacity: this.capacity,
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
