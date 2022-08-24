<template>
  <CustomTemplate>
    <div id="login-form" class="flex flex-col gap-4 mb-8">
      <input
        type="text"
        placeholder="Email"
        class="input input-bordered w-full max-w-xs"
      /><input
        type="text"
        placeholder="Mot de passe"
        class="input input-bordered w-full max-w-xs"
      />
      <button class="btn">Login</button>
    </div>

    <div id="signup-form" class="flex flex-col gap-4">
      <div class="flex gap-2">
        <input
          type="text"
          placeholder="Email"
          class="input input-bordered w-full max-w-xs"
        /><input
          type="text"
          placeholder="Mot de passe"
          class="input input-bordered w-full max-w-xs"
        />
      </div>
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
      <button class="btn">Sign up</button>
    </div>
  </CustomTemplate>
</template>

<script>
import CustomTemplate from '~/components/CustomTemplate.vue'

export default {
  name: 'AccountPage',
  components: { CustomTemplate },
  data: () => ({
    accommodations: [],
  }),
  async fetch() {
    this.accommodation = await fetch(
      'http://localhost:3001/accommodations/'
    ).then((res) => res.json())
  },
}
</script>
