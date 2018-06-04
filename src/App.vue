<template>
  <div class="container">
    <progress-bar :postCount="notes.length" :maxNotes="maxNotes"></progress-bar>
    <new-post-form @newPost="newPost"></new-post-form>
    <note-board :notes="notes"  @removePost="removePost"></note-board>
  </div>
</template>

<script>
import NoteBoard from "./components/NotesBoard";
import NewPostForm from "./components/NewPostForm";
import ProgressBar from "./components/ProgressBar";

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
      if (this.notes.length >= this.maxNotes) {
        alert("Please delete a post first!");
        return;
      }
      this.notes.push(post);
    },
    removePost(key) {
      this.notes.splice(key, 1);
      this.savePosts();
    }
  },
  components: {
    NoteBoard,
    NewPostForm,
    ProgressBar
  }
};
</script>

<style lang="scss">
</style>
