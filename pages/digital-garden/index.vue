<template>
  <div>
    <h1 class="text-center text-4xl mt-10 mb-3">My Digital Garden</h1>
    <hr class="border-green-300 border-1" />
    <List :items="plants" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

import List from '../../components/List.vue'

export default Vue.extend({
  components: {
    List,
  },
  async asyncData(ctx) {
    const plants = await ctx
      .$content('digital-garden')
      .sortBy('publishOn', 'desc')
      .fetch()

    return {
      plants,
    }
  },
})
</script>
