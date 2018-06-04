<template>
  <div class="container">
    <progress-bar :postCount="notes.length" :maxNotes="maxNotes"></progress-bar>
    <new-post-form @newPost="newPost"></new-post-form>
    <note-board :notes="notes"  @removePost="removePost"></note-board>
    <div class="row">
      <div class="col-12 text-center" v-if="notes.length > 0">
        <div class="alert alert-info">
          Click on a post to delete it!
        </div>
      </div>
    </div>
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
      notes: [],
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
      this.savePosts();
    },
    removePost(key) {
      this.notes.splice(key, 1);
      this.savePosts();
    },
    savePosts() {
      let parsed = JSON.stringify(this.notes);
      localStorage.setItem("notes", parsed);
    }
  },
  mounted() {
    if (localStorage.getItem("notes")) {
      try {
        this.notes = JSON.parse(localStorage.getItem("notes"));
        if (this.notes.length === 0) {
          this.notes.push("Try To Post a New Note!");
          let parsed = JSON.stringify(this.notes);
          localStorage.setItem("notes", parsed);
        }
      } catch (e) {
        localStorage.removeItem("notes");
      }
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
