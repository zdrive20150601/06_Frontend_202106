<template>
    <div>
        <Child :message="title" :count="state.num" />
        <button @click="countNum">2倍</button>
    </div>
</template>

<script>
import { defineComponent, computed, reactive, ref } from 'vue'
import Child from './Child.vue'

export default defineComponent ({
    name: 'Parent',
    components: { Child },
    setup () {
        const title = ref('タイトル')
        const state = reactive({
                num: 1,
                numState: computed(() => state.num * 2 )
            })
        const countNum = () => state.num++
        console.log(state.num)
        return { title, state, countNum, console }
    }
})
</script>