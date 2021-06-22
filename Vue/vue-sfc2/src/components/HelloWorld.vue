<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <CopyDocs :docs="copy" />
    <Parent />
    <RefLinks />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import RefLinks from './RefLinks.vue'
import CopyDocs from './CopyDocs.vue'
import Parent from './Parent.vue'

export default defineComponent({
  name: 'HelloWorld',
  components: { RefLinks, CopyDocs, Parent },
  props: {
    msg: String,
  },
  setup() {
      const copy = ref('For a guide and recipes on how to configure / customize this project,')
      return { copy }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
