<template>
  <div class="row">
    <note-block
      v-for="(note, index) in notes"
      :key="index"
      @click.native="removePost(index)">
      {{note}}
      </note-block>
  </div>
</template>

<script>
import NoteBlock from "./NoteBlock";
export default {
  props: ["notes"],
  methods: {
    removePost(key) {
      this.$emit("removePost", key);
    }
  },
  components: {
    NoteBlock
  }
};
</script>

<style lang="scss">
</style>
