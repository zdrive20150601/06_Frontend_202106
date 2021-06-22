<template>
    <p>
        {{ docs }}<br>
        check out the
        <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent ({
    name: 'CopyDocs',
    props: {
        docs: {
            type: String,
            required: true
        }
    }
})
</script>