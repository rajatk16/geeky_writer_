<template>
  <div>
    <h1 class="text-center text-4xl mt-10">My Digital Garden</h1>
    <p>Filtered By: {{ $route.params.tag }}</p>
    <hr class="border-green-300 border-1" />
    <List :items="plants" />
  </div>
</template>

<script>
import Vue from 'vue'

import List from '../../../components/List.vue'
export default Vue.extend({
  components: {
    List,
  },
  async asyncData(ctx) {
    const plants = await ctx
      .$content('digital-garden')
      .where({
        tags: {
          $contains: ctx.route.params.tag,
        },
      })
      .sortBy('publishOn', 'desc')
      .fetch()

    return {
      plants,
    }
  },
})
</script>
