<template>
  <div class="container">
    <div class="notepad-container" >
      <header class="text-center"><h2>V-Notepad</h2></header>
      <section class="notepad-contents" v-if="isEditorEnabled === false">
        <b-list-group>
          <b-list-group-item button v-for="note in notes" :key="note.title">{{note.title}}</b-list-group-item>
        </b-list-group>
      </section>
      <section class="notepad-editor" v-else-if="isEditorEnabled === true">
        <h3>Note Editor</h3>
      </section>
      <div class="plus-icon-container" @click="addNoteHandler">
        <add-note-button></add-note-button>
      </div>
    </div>
  </div>
</template>

<script>
import AddNoteButton from './components/AddNoteButton.vue';

export default {
  name: 'App',
  components: {
    AddNoteButton
  },
  data() {
    return {
      notes:[
        {
          title: "Checklist for Store",
          type: "checklist",
          data: [
            "Potatoes",
            "Eggs",
            "Cheese",
            "Milk"
          ]
        },
        {
          title: "Note for Thursday",
          type: "note",
          data: "This is a note with really good stuff!"
        }
      ],
      isEditorEnabled: false
    }
    
  },
  methods: {
      addNoteHandler() {
        this.isEditorEnabled = !this.isEditorEnabled;
      }
    }
  
}
</script>

<style>
.container {
  position: absolute;
  top: 30%;
  left:50%;
  transform: translate(-50%, -50%);
  
}
.notepad-container {
  border:1px solid black;
  border-radius:15px;
  height:300px;
  overflow:hidden!important;
}
header {
  border-bottom:1px solid black;
  padding:5px;
  margin:0;
  background-color:#508991;
}
section.notepad-contents {
  _padding:15px;
}
.plus-icon-container {
  position: absolute;
  bottom: 10%;
  right:10%;
}

</style>
