<template>
  <main>
    <div class="container">
      <div class="row py-5 offset-1">
        <div
          v-for="(card, index) in cards"
          :key="index"
          class="
            col-sm-4 col-md-3 col-lg-2
            justify-content-center
            text-center
            d-flex
            m-2
          "
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
  props: ["selectedGenre"],
  data() {
    return {
      cards: [],
    };
  },
  computed: {
    filteredCard() {
      return this.cards.filter((card) => {
        if (card.genre === this.selectedGenre) {
          return true;
        } else {
          return false;
        }
      });
    },
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

        const genres = [];
        this.cards.forEach((card) => {
          const { genre } = card;
          if (!genres.includes(genre)) genres.push(genre);
        });
        this.$emit("genres", genres);
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