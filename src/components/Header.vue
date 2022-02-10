<template>
  <header class="d-flex align-items-center">
    <img src="../assets/Logo-della-Spotify.png" alt="Logo-Spotify" />
  </header>
</template>

<script>
export default {
  name: "Header",
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