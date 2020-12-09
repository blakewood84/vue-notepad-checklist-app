<template>
  <div class="body">
    <div class="notepad-container h-75 w-75">
      <header class="header d-flex justify-content-center align-items-center">
        <h4>Light Notepad v1</h4>
      </header>
      <section class="notepad-content" v-if="editorIsOpen === false">
        <note-list
          v-for="note in notes"
          :key="note.id"
          :note="note"
        ></note-list>
        <add-note-button @open-editor="openNewEditor"></add-note-button>
      </section>

      <section class="notepad-editor" v-if="editorIsOpen === true">
        <save-button></save-button>
      </section>

      <section v-if="noteIsOpen === true">
       <show-note @open-note="readNote"></show-note>
      </section>

    </div>
  </div>
</template>
<script>
import AddNoteButton from "./components/AddNoteButton.vue";
import NoteList from "./components/NoteList.vue";
import SaveButton from './components/SaveButton.vue';
import ShowNote from './components/ShowNote';

export default {
  components: {
    NoteList,
    AddNoteButton,
    SaveButton,
    ShowNote
  },
  data() {
    
    return {
      editorIsOpen: false,
      noteIsOpen: false,
      notes: [
        {
          id: 1,
          title: "1st Note",
          body: "This is a note",
          date: "10/17/20",
        },
        {
          id: 2,
          title: "2nd Note",
          body: "This is a note",
          date: "11/17/20",
        },
      ],
    };
  },
  methods: {
    openNewEditor() {
      this.editorIsOpen = !this.editorIsOpen;
      
    },
    readNote() {
      this.noteIsOpen = !this.noteIsOpen
      }
    }
};
</script>
<style>
.body {
  height: 100vh;
  width: 100%;
  position: relative;
}
.notepad-container {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border: 1px solid black;
  border-radius: 3px;
}
.header {
  height: 10%;
  border-bottom: 1px solid black;
  background-color: blanchedalmond;
}

.notepad-content {
  height: 90%;
}
</style>
