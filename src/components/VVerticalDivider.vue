<template>
  <div class="divider"></div>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  name: "VVerticalDivider"
})
</script>

<style scoped>
.divider {
  @apply w-1 border-r border-r-white;
}
</style>