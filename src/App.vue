<template>
  <div>
    <Header :genres="genres" @selected-genre="setGenreOption" />
    <Main @genres="setGenres" :selectedGenre="selectedGenre" />
  </div>
</template>

<script>
import Main from "./components/Main.vue";
import Header from "./components/Header.vue";
export default {
  name: "App",
  data() {
    return {
      genres: [],
      selectedGenre: "",
    };
  },
  components: {
    Header,
    Main,
  },
  methods: {
    setGenres(genres) {
      this.genres = genres;
    },

    setGenreOption(genre) {
      this.selectedGenre = genre;
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
