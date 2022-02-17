<template>
  <header class="d-flex align-items-center justify-content-between px-5">
    <img src="../assets/Logo-della-Spotify.png" alt="Logo-Spotify" />
    <!-- <h1 class="text-white">La mia libreria Spotify</h1> -->
    <div><SelectGenre :genres="genres" @change-genre="selectedGenre" /></div>
    <!-- :genre="card.genre" da aggiungere in selectgenre quando passo le info con emit() -->
  </header>
</template>

<script>
import SelectGenre from "./SelectGenre.vue";
export default {
  name: "Header",
  props: ["genres"],
  data() {
    return {};
  },
  components: {
    SelectGenre,
  },
  methods: {
    selectedGenre(selectedGenre) {
      this.$emit("selected-genre", selectedGenre);
    },
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