<template>
  <div>
    <select
      class="form-select bg-select text-white"
      aria-label="Default select example"
    >
      <option selected>Tutti i generi musicali</option>
      <option value="1">Rock</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "SelectGenre",
};
</script>

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap.scss";
.bg-select {
  background-color: #1e2d3b;
  border-color: #1e2d3b;
}
</style>