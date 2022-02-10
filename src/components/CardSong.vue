<template>
  <div>
    <div
      v-for="(card, index) in cards"
      :key="index"
      class="
        col-2
        offset-1
        bg-card-song
        d-flex
        flex-column
        align-items-center
        text-center
      "
    >
      <div class="card-song">
        <img :src="poster" alt="song" />
      </div>
      <div class="card-description">
        <h4 class="text-white">{{ title }}</h4>
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
import axios from "axios";
export default {
  name: "Card",
  data() {
    return {
      cards: [],
    };
  },
  methods: {
    // getSongs() {
    //   axios
    //     .get("https://flynn.boolean.careers/exercises/api/array/music")
    //     .then((res) => {
    //       this.cards = res.data.response;
    //     });
    // },
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.cards = res.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap.scss";
.bg-card-song {
  background-color: #2e3a46;
}
.card-description {
  padding: 20px;
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