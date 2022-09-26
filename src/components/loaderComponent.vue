<template>
  <div class="background d-flex flex-column justify-content-center align-items-center">
  <img src="@/assets/spotify-logo.png" alt="">

    <div class="spinner-border text-success spinner-border-lg" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "@/variables";

div.background {
  position: absolute;
  background-color: $primary-color;
  width: 100%;
  height: 100%;
  img {
    width: 200px;
    margin: 4rem
  }
  .spinner-border {
    width: 100px;
    height: 100px;
    color: green
  }
}
</style>
