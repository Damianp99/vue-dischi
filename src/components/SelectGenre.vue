<template>
  <div class="d-flex">
    <div class="px-3">
      <select
        class="form-select bg-select text-white"
        aria-label="Default select example"
        v-model="selectedGenre"
        @change="changeGenre"
      >
        <option selected>Tutti i generi musicali</option>
        <option v-for="(genre, index) in genres" :key="index" value="1">
          {{ genre }}
        </option>
      </select>
    </div>
    <div><button class="btn btn-genre text-white">Cerca</button></div>
  </div>
</template>

<script>
export default {
  name: "SelectGenre",
  props: ["genres"],
  data() {
    return {
      selectedGenre: "",
    };
  },
  methods: {
    changeGenre() {
      this.$emit("change-genre", this.selectedGenre);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap.scss";
.bg-select {
  background-color: #1e2d3b;
  border-color: #1e2d3b;
}

.btn-genre {
  background-color: #1e2d3b;
}
</style>