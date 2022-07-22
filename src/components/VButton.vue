<template>
  <a :href="href">
    <div class="bg-black py-3 px-5 ring-2 ring-white ring-opacity-20 rounded-md bg-opacity-30 hover:bg-opacity-60 hover:ring-opacity-30 shadow-md hover:shadow-lg
        hover:rounded-lg transition-all duration-150 font-medium text-white">
      <slot></slot>
    </div>
  </a>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  name: "VButton",
  props: ['href'],
  setup() {

  }
})
</script>

<style scoped>

</style>