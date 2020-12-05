<template>
  <div class="add-note-container" @click="openEditor">
    <b-icon-plus-circle></b-icon-plus-circle>
  </div>
</template>

<script>
import {BIconPlusCircle} from 'bootstrap-vue';
export default {
  emits: ['open-editor'],
  components: {
    BIconPlusCircle
  },
  methods: {
    openEditor() {
      console.log('hello');
      this.$emit('open-editor');
    }
  }
}
</script>
<style scoped>
  .add-note-container {
    position: absolute;
    bottom:10%;
    right:10%;
    font-size:3rem;
    cursor: pointer;
  }
</style>