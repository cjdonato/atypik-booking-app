<template>
  <CustomTemplate>
    <p class="mb-8">Ajout d'hebergement</p>

    <div
      id="add-accom-form"
      class="flex flex-col gap-4 w-128"
    >
      <select v-model="type" class="select select-bordered w-full" required>
        <option selected>Category1</option>
        <option>Category2</option>
        <option>Category3</option>
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
      <button class="btn" @click="add_accommodation">Ajouter</button>
    </div>
  </CustomTemplate>
</template>

<script>
import CustomTemplate from '~/components/CustomTemplate.vue'

export default {
  name: 'AddAccommodationPage',
  components: { CustomTemplate },
  data: () => ({
    type: 'Category1',
    name: '',
    price: '',
    capacity: '',
    description: '',
    errored: false,
  }),
  methods: {
    async add_accommodation() {
      const userID = JSON.parse(localStorage.getItem('user')).id
      await this.$axios
        .$post('/accommodation/add', {
          type: this.type,
          name: this.name,
          description: this.description,
          price: this.price,
          capacity: this.capacity,
          image: 'https://placeimg.com/400/400/arch',
          userID: userID,
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
