<template>
  <CustomTemplate>
    <!-- <Profile /> -->
    <Profile v-if="this.$store.state.auth" />
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
import Profile from '~/components/Profile.vue'

export default {
  name: 'AccountPage',
  components: { CustomTemplate, Login, Register, Profile },
}
</script>
