<template>
  <div class="mt-10 ml-20 w-10/12">
    <ul v-for="listItem in items" :key="listItem.slug">
      <ListItem :item="listItem" />
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import type { PropType } from 'vue'

import { Item } from '../interfaces/item'
import ListItem from './ListItem.vue'
export default Vue.extend({
  components: {
    ListItem,
  },
  props: {
    items: {
      type: Array as PropType<Item[]>,
      required: true,
    },
  },
})
</script>
