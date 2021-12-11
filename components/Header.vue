<template>
  <header class="bg-gray-900">
    <nav class="container px-6 py-4 mx-auto flex justify-between items-center">
      <div class="flex items-center justify-between">
        <NuxtLink to="/">
          <p
            class="
              text-xl
              transition-colors
              duration-300
              transform
              hover:text-green-400
            "
          >
            geeky_writer_
          </p>
        </NuxtLink>
      </div>
      <div
        class="
          flex flex-col
          mt-2
          space-y-4
          md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0
        "
      >
        <NuxtLink
          to="/digital-garden"
          class="
            text-sm
            font-medium
            transition-colors
            duration-300
            transform
            hover:text-green-400
          "
        >
          Digital Garden
        </NuxtLink>
      </div>
    </nav>
  </header>
</template>

<script>
import Vue from 'vue'
export default Vue.extend({})
</script>
