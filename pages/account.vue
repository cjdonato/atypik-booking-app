<template>
  <CustomTemplate>
    <Login />
    <Register />
  </CustomTemplate>
</template>

<script>
import CustomTemplate from '~/components/CustomTemplate.vue'
import Login from '~/components/Login.vue';
import Register from '~/components/Register.vue';

export default {
  name: 'AccountPage',
  components: { CustomTemplate, Login, Register },
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
