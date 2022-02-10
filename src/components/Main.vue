<template>
  <main>
    <div class="container">
      <div class="row py-5">
        <CardSong />
      </div>
    </div>
  </main>
</template>

<script>
import CardSong from "./CardSong.vue";
export default {
  name: "Main",
  components: {
    CardSong,
  },
};
</script>

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap.scss";
main {
  height: calc(100vh - 80px);
  background-color: #1e2d3b;
}
</style>