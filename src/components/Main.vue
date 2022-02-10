<template>
  <main>
    <div class="container">
      <div class="row py-5 offset-1">
        <div
          v-for="(card, index) in cards"
          :key="index"
          class="col-2 justify-content-center text-center d-flex m-2"
        >
          <CardSong
            :poster="card.poster"
            :title="card.title"
            :author="card.author"
            :year="card.year"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import CardSong from "./CardSong.vue";

export default {
  name: "Main",
  components: {
    CardSong,
  },
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

<style lang="scss" >
@import "~bootstrap/scss/bootstrap.scss";
main {
  height: calc(100vh - 80px);
  background-color: #1e2d3b;
}
</style>