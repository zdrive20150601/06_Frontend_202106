<template>
    <div>
        <h1>{{ message }}</h1>
        <p>カウント数: {{ count }}</p>
    </div>
</template>

<script>
import { defineComponent, computed } from 'vue'

export default defineComponent({
    name: 'Child',
    props: {
        message: {
            type: String,
            required: true
        },
        count: {
            type: Number,
            default: 0
        }
    },
    setup (props){
        const count = computed(() => props.count * 2)
        return { count }
    }
})
</script>