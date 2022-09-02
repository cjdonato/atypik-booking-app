<template>
  <div id="login-form" class="flex flex-col gap-4 mb-8">
    <div v-if="errored" class="alert alert-error shadow-lg">
      <span>Le compte n'existe pas</span>
    </div>
    <input
      v-model="email"
      type="text"
      placeholder="Email"
      class="input input-bordered w-full max-w-xs"
    /><input
      v-model="password"
      type="password"
      placeholder="Mot de passe"
      class="input input-bordered w-full max-w-xs"
    />
    <button class="btn" @click="login">Login</button>
  </div>
</template>

<script>
export default {
  name: 'LoginComponent',
  data: () => ({
    email: '',
    password: '',
    errored: false,
  }),
  methods: {
    async login() {
      await this.$axios
        .$post('/user/', {
          username: this.email,
          password: this.password,
        })
        .then((response) => {
          console.log(response)
          this.errored = false
          const auth = response
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
