<template>
  <div class="flex items-center">
    <div class="h-2 w-full">
      <div class="h-full bg-gray-300 rounded-full overflow-x-hidden">
        <div class="h-full rounded-full transition-all duration-700" :style="{width: isVisible ? value + '%' : '0px'}" ref="target" :class="pgbClass"></div>
      </div>
    </div>
    <span class="text-xs ml-2">{{value}}%</span>
  </div>
</template>

<script lang="ts">
import {computed, defineComponent, onMounted, ref, watch, watchEffect} from "vue";
import {useElementVisibility} from "@vueuse/core";

export default defineComponent({
  name: "VProgressBar",
  props: {
    value: {
      required: true,
      type: Number,
      default: 0
    },
    pgbClass: {
      required: false,
      type: String,
      default: 'bg-red-800'
    }
  },
  setup(props) {

    const target = ref()

    const isVisible = useElementVisibility(target)

    return {
      target,
      isVisible
    }
  }
})
</script>

<style scoped>

</style>