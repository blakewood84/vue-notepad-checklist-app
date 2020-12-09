<template>
<div>
    <b-list-group>
      <b-list-group-item button @click="openNote"
        >{{ note.title }} - {{ note.date }}</b-list-group-item
      >
    </b-list-group>
    </div>
</template>
<script>
export default {
  emits: ['open-note'],
  props: {
    note: {
      required: true,
    },
  },
  methods: {
    openNote() {
      this.$emit('open-note');
      alert("clicked from NoteList");

    },
  },
};
</script>
