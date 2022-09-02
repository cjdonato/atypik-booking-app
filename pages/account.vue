<template>
  <CustomTemplate>
    {{ this.$store.state.auth }}
    <div v-if="this.$store.state.auth">
      You are logged in
      <button class="btn" @click="logout">Logout</button>
    </div>
    <div v-else>
      <Login />
      <Register />
    </div>
  </CustomTemplate>
</template>

<script>
import CustomTemplate from '~/components/CustomTemplate.vue'
import Login from '~/components/Login.vue'
import Register from '~/components/Register.vue'

export default {
  name: 'AccountPage',
  components: { CustomTemplate, Login, Register },
  data: () => ({
    accommodations: [],
  }),
  methods: {
    async logout() {
      this.$store.commit('setAuth', null)
    },
  },
}
</script>
