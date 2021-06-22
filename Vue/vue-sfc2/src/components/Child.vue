<template>
    <button @click="handleClick">{{ btnName }} {{ count }}</button>
</template>

<script>
import { defineComponent, props, context } from 'vue';

export default defineComponent({
    name: 'Child',
    props: {
        count: {
            type: Number
        },
        btnName: {
            type: String
        }
    },
    setup (props, { emit }) {
    const handleClick = () => {
        emit('increment-event', props.count + 1)
        emit('decrement-event', props.count - 1)
    }
    return { handleClick }
    }
})
</script>

<style scoped>
  button {
    padding: 15px;
    font-size: 1.8rem;
    margin-left: 10px;
  }
</style>