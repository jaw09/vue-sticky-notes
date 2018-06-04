<template>
  <div class="row">
    <note-block
      v-for="(note, index) in notes"
      :key="index">
      {{note}}
      </note-block>
  </div>
</template>

<script>
import NoteBlock from "./NoteBlock";
export default {
  props: ["notes"],
  components: {
    NoteBlock
  }
};
</script>

<style lang="scss">
</style>
