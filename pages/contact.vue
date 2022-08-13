<template>
  <CustomTemplate>
    <div id="contact-form" class="flex flex-col gap-4">
      <div class="flex gap-2">
        <input
          type="text"
          placeholder="Nom"
          class="input input-bordered w-full max-w-xs"
        /><input
          type="text"
          placeholder="Prénom"
          class="input input-bordered w-full max-w-xs"
        />
      </div>
      <div class="flex gap-2">
        <input
          type="text"
          placeholder="Email"
          class="input input-bordered w-full max-w-xs"
        /><input
          type="text"
          placeholder="Téléphone"
          class="input input-bordered w-full max-w-xs"
        />
      </div>

      <textarea
        class="textarea textarea-bordered"
        placeholder="Message"
      ></textarea>
      <button class="btn">Envoyer</button>
    </div>
    <Newsletter />
  </CustomTemplate>
</template>

<script lang="ts">
import Vue from 'vue'
import CustomTemplate from '~/components/CustomTemplate.vue'
import Newsletter from '~/components/Newsletter.vue'

export default Vue.extend({
  name: 'ContactPage',
  components: { CustomTemplate, Newsletter },
})
</script>
