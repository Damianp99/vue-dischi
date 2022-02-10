<template>
  <div>
    <div class="bg-card-song">
      <div class="card-song">
        <img :src="poster" alt="song" />
      </div>
      <div class="card-description">
        <span class="text-white fw-bold">{{ title }}</span>
        <div class="text-muted h5">
          <span>{{ author }}</span>
        </div>
        <div class="text-muted">
          <span>{{ year }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["poster", "title", "author", "year"],
};
</script>

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap.scss";

.bg-card-song {
  background-color: #2e3a46;
}
.card-description {
  height: 150px;
  width: 200;
}

.card-song {
  height: 200px;
  width: 200px;
}
img {
  padding: 15px;
  height: 200px;
  width: 200px;
}
</style>