<template>
  <div class="bg-gray-800 text-white">
    <Header />
    <div class="container m-auto p-4 h-screen">
      <Nuxt />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '../components/Header.vue'

export default Vue.extend({
  components: {
    Header,
  },
})
</script>
