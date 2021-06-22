<template>
<div>
    <Child @increment-event="state.inc = $event" :count="state.inc" :btnName="state.incName"  />
    <Child @decrement-event="state.dec = $event" :count="state.dec" :btnName="state.decName" />
</div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue';
import Child from './Child.vue'

export default defineComponent({
    name: 'Parent',
    components: { Child },
    setup() {
        const state = reactive({
            inc: 0,
            dec: 0,
            incName: '加算',
            decName: '減算'
        })
        return { state }
    }
});
</script>