<template>
  <div class="flex flex-col h-screen">
    <Header class="h-10" />

    <div class="mb-auto flex flex-col items-center sm:px-6 lg:px-8 w-full">
      <slot> </slot>
    </div>

    <Footer />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Footer from './Footer.vue'
import Header from '~/components/Header.vue'

export default Vue.extend({
  name: 'CustomTemplateComponent',
  components: { Header, Footer },
})
</script>
