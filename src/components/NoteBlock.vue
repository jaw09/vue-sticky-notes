<template>
  <div class="col-12 col-md-6 col-lg-4 col-xl-3 my-3">
    <div class="card">
      <div class="card-body note">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
.note {
  min-height: 150px;
  font-family: "Arizonia", cursive;
  font-size: 24px;
  color: #6e6e6e;
  background: #fdf470;
  cursor: pointer;
  &:hover {
    background: #fe8a8b;
  }
}
</style>
