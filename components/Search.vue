<template>
  <!-- <div class="flex flex-col items-center px-24 py-8 w-screen bg-green-800"> -->
  <div class="flex flex-col items-center px-24 py-8 w-screen">
    <input
      type="text"
      placeholder="Quel type d'habtitat souhaitez-vous louer"
      class="input input-bordered w-10/12 m-2"
    />
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

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'SearchComponent',
})
</script>
