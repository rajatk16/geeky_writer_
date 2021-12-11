<template>
  <li
    class="
      py-5
      pl-5
      border-2
      my-5
      rounded
      hover:border-green-300 hover:transition-opacity
      duration-500
      hover:shadow-2xl
    "
  >
    <NuxtLink :to="`${item.dir}/${item.slug}`">
      <h2 class="text-2xl">
        {{ item.title }}
      </h2>
      <NuxtContent :document="{ body: item.excerpt }" />
    </NuxtLink>
    <ul v-if="item.tags" class="flex flex-row mt-5">
      <li
        v-for="tag in item.tags"
        :key="tag"
        class="
          mx-1
          px-2
          text-sm
          border-2
          hover:border-green-300
          rounded-full
          transition-colors
          duration-300
        "
      >
        <NuxtLink :to="`${item.dir}/tag/${tag}`">
          {{ tag }}
        </NuxtLink>
      </li>
    </ul>
  </li>
</template>

<script lang="ts">
import Vue from 'vue'
import type { PropType } from 'vue'

import { Item } from '../interfaces/item'

export default Vue.extend({
  props: {
    item: {
      type: Object as PropType<Item>,
      required: true,
    },
  },
})
</script>
