<template>
  <div class="row my-5">
    <h3>Post Added</h3>
    <div class="progress col-12 p-0 mt-2">
      <div class="progress-bar progress-bar-striped" role="progressbar" aria-valuenow="10" aria-valuemin="0"
        aria-valuemax="100" :style="{width: progress}"><span class="p-2">{{postCount}} / {{maxNotes}}</span></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    postCount: Number,
    maxNotes: Number
  },
  computed: {
    progress() {
      return this.postCount / this.maxNotes * 100 + "%";
    }
  }
};
</script>

<style lang="scss">
</style>
