<template>
  <!-- <div class="flex flex-col items-center px-24 py-8 w-screen bg-green-800"> -->
  <div class="flex flex-col items-center px-24 py-8 w-screen">
    <!-- <input
      type="text"
      placeholder="Quel type d'habtitat souhaitez-vous louer"
      class="input input-bordered w-10/12 m-2"
    /> -->
    <select v-model="type" class="select select-bordered w-10/12 m-2" required>
      <option disabled selected>Quel type d'habtitat souhaitez-vous louer</option>
      <option >Category1</option>
      <option>Category2</option>
      <option>Category3</option>
    </select>
    <input
      type="text"
      placeholder="Où souhaitez-vous vous évader"
      class="input input-bordered w-10/12 m-2"
    />
    <input
      type="text"
      placeholder="A combien voyagez-vous"
      class="input input-bordered w-10/12 m-2"
    />

    <button class="btn mt-2">Rechercher</button>
  </div>
</template>

<script>
export default {
  name: 'SearchComponent',
  data: () => ({
    type: "Quel type d'habtitat souhaitez-vous louer",
  }),
}
</script>
