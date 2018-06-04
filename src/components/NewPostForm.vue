<template>
  <div class="row">
    <form class="col-12 p-0">
      <div class="col-12 col-md-8 offset-md-2 col-xl-6 offset-md-3 form-group">
        <label for="new-post">New Post</label>
        <textarea id="new-post" rows="3" class="form-control" v-model="post"></textarea>
      </div>
      <div class="col-4 col-md-3 offset-md-2 offset-md-3 form-group">
        <button class="btn btn-outline-primary" @click.prevent="newPost">New Post</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: ""
    };
  },
  methods: {
    newPost() {
      this.$emit("newPost", this.post);
      this.post = "";
    }
  }
};
</script>

<style lang="scss">
</style>
