<template>
  <div id="signup-form" class="flex flex-col gap-4">
    <div v-if="errored" class="alert alert-error shadow-lg">
      <span>Email deja pris</span>
    </div>
    <div class="flex gap-2">
      <input
        v-model="email"
        type="text"
        placeholder="Email"
        class="input input-bordered w-full max-w-xs"
      /><input
        v-model="password"
        type="text"
        placeholder="Mot de passe"
        class="input input-bordered w-full max-w-xs"
      />
    </div>
    <div class="flex gap-2">
      <input
        v-model="nom"
        type="text"
        placeholder="Nom"
        class="input input-bordered w-full max-w-xs"
      /><input
        v-model="prenom"
        type="text"
        placeholder="Prénom"
        class="input input-bordered w-full max-w-xs"
      />
    </div>
    <button class="btn" @click="register">Sign up</button>
  </div>
</template>

<script>
export default {
  name: 'RegisterComponent',
  data: () => ({
    email: '',
    password: '',
    nom: '',
    prenom: '',
    errored: false,
  }),
  methods: {
    async register() {
      await this.$axios
        .$post('/user/add', {
          username: this.email,
          password: this.password,
        })
        .then((response) => {
          console.log(response)
          this.errored = false
          const auth = response.user
          this.$store.commit('setAuth', auth)
        })
        .catch((error) => {
          console.log(error)
          this.errored = true
        })
    },
  },
}
</script>
