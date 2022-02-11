<template>
  <header class="d-flex align-items-center justify-content-between px-5">
    <img src="../assets/Logo-della-Spotify.png" alt="Logo-Spotify" />
    <div><SelectGenre /></div>
  </header>
</template>

<script>
import SelectGenre from "./SelectGenre.vue";
export default {
  name: "Header",
  components: {
    SelectGenre,
  },
};
</script>

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap.scss";
header {
  background-color: #2e3a46;
  height: 80px;
}
img {
  width: auto;
  height: 50px;
}
</style>