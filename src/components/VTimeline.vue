<template>

</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'VTimeline',
    props: {
        datas: {
            required: true,
            type: Array,
            default: []
        }
    }
})
</script>