<template>
  <div>
    <b-icon
      :icon="this.hoverHandler()"
      @mouseover="isHovered = true"
      @mouseleave="isHovered = false"
      class="icon-style"
    ></b-icon>
  </div>
</template>

<script>
import { BIcon } from "bootstrap-vue";
export default {
  name: "AddNoteButton",
  components: {
    BIcon,
  },
  data() {
    return {
      isHovered: false,
    };
  },
  methods: {
    hoverHandler() {
      if (this.isHovered === true) {
        return "plus-circle-fill";
      }
      else if (this.isHovered === false) {
          return "plus-circle";
      }
    }
  },
};
</script>
<style scoped>
    .icon-style {
        width:50px;
        height:50px;
        color:#508991;
        cursor: pointer;
    }
</style>