<template>
  <div class="flex flex-col h-screen">
    <Header class="h-10" />

    <div class="mb-auto flex flex-col items-center sm:px-6 lg:px-8 w-full">
      <Search />
    </div>

    <Footer />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Search from '../components/Search.vue'
import Footer from '../components/Footer.vue'
import Header from '~/components/Header.vue'

export default Vue.extend({
  name: 'ContactPage',
  components: { Header, Footer, Search },
})
</script>
