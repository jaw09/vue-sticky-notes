<template>
  <div class="container">
    <note-board :notes="notes"></note-board>
  </div>
</template>

<script>
import NoteBoard from "./components/NotesBoard";

export default {
  name: "App",
  data() {
    return {
      notes: ["Test to View"],
      maxNotes: 10
    };
  },
  components: {
    NoteBoard
  }
};
</script>

<style lang="scss">
</style>
