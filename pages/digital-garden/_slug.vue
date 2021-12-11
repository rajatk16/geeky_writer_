<template>
  <div>
    <h1 class="text-4xl text-center mt-20">{{ plant.title }}</h1>
    <div class="mt-20">
      <NuxtContent :document="plant" />
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
export default Vue.extend({
  async asyncData(ctx) {
    const plant = await ctx
      .$content(`digital-garden/${ctx.route.params.slug}`)
      .fetch()
    return {
      plant,
    }
  },
})
</script>
