<template>
  <!-- <div class="flex w-screen px-48 py-12 bg-orange-400"> -->
  <div class="flex w-screen px-48 py-12">
    <p class="w-1/2 pr-8 text-justify">
      Nulla interdum consequat mi. In condimentum elit justo, ut efficitur nunc
      ultricies non. Nunc interdum est at ipsum eleifend dictum. Cras lorem
      tellus, ornare et tempus ac, lobortis non risus. Cras faucibus augue elit,
      sed iaculis felis porttitor nec. Morbi eu dolor quis nunc sollicitudin
      maximus eu tempor magna. Duis dignissim odio vel nisl convallis, sed
      vulputate risus dapibus. Nulla quam leo, blandit ac eros eu, varius mollis
      sem. Nam iaculis porttitor purus et malesuada.
    </p>
    <div class="flex flex-col w-1/2">
      <input
        type="text"
        placeholder="Votre email pour recevoir nos Newsletters"
        class="input input-bordered w-full my-2"
      />
      <button class="btn mt-4">Valider</button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'NewsletterComponent',
})
</script>
