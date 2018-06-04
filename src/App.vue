<template>
  <div class="container">
    <new-post-form @newPost="newPost"></new-post-form>
    <note-board :notes="notes"></note-board>
  </div>
</template>

<script>
import NoteBoard from "./components/NotesBoard";
import NewPostForm from "./components/NewPostForm";

export default {
  name: "App",
  data() {
    return {
      notes: ["Test to View"],
      maxNotes: 10
    };
  },
  methods: {
    newPost(post) {
      if (!post) {
        alert("No content!");
        return;
      }
      this.notes.push(post);
    }
  },
  components: {
    NoteBoard,
    NewPostForm
  }
};
</script>

<style lang="scss">
</style>
