<template>
  <div class="flex flex-col">
    You are logged in {{ this.$store.state.auth }}
    <!-- <div id="modify-form" class="flex flex-col gap-4">
      <div v-if="errored" class="alert alert-error shadow-lg">
        <span>Probl</span>
      </div>
      <div class="flex gap-2">
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
      <button class="btn" @click="register">Modify</button>
    </div> -->
    <MyAccommodations />
    <MyReservations />
    <button class="btn mb-4" @click="logout">Logout</button>
  </div>
</template>

<script>
import MyAccommodations from './MyAccommodations.vue'
import MyReservations from './MyReservations.vue'

export default {
  name: 'ProfileComponent',
  components: { MyAccommodations, MyReservations },
  data: () => ({
    email: '',
    password: '',
    nom: '',
    prenom: '',
    errored: false,
  }),
  methods: {
    // TODO HEHE
    // async modify() {
    //     await this.$axios
    //       .$put('/user/', {
    //         username: this.email,
    //         password: this.password,
    //       })
    //       .then((response) => {
    //         console.log(response)
    //         this.errored = false
    //         const auth = response.user
    //         this.$store.commit('setAuth', auth)
    //       })
    //       .catch((error) => {
    //         console.log(error)
    //         this.errored = true
    //       })
    // },
    async logout() {
      this.$store.commit('setAuth', null)
    },
  },
}
</script>
