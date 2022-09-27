<template>
  <div class="container mt-5">
    <search-component
      :genres="genres"
      @searchGenre="selectedGenres"
      @searchAuthor="selectedAuthor"
    />

    <div class="row justify-content-center">
      <card-component
        class="col-lg-2 col-md-3 col-sm-8 col-12 cards"
        v-for="(poster, index) in showSelected"
        :key="index"
        :author="poster.author"
        :img="poster.poster"
        :title="poster.title"
        :year="poster.year"
      />
    </div>
  </div>
</template>

<script>
import cardComponent from "./cardComponent.vue";
import SearchComponent from "./searchComponent.vue";
export default {
  components: { cardComponent, SearchComponent },

  data() {
    return {
      posters: [],
      genres: [],
      selectGenre: "",
      selectAuthor: "",
    };
  },
  props: {
    data: Array,
  },
  created() {
    this.posters = this.data;
    this.genres = [...new Set(this.posters.map((value) => value.genre))];
  },
  computed: {
    showSelected() {
      let arr = [...this.posters];
      if (this.selectGenre !== "") {
        arr = this.posters.filter((value) => {
          if (value.genre === this.selectGenre) return true;
        });
      }
      if (this.selectAuthor !== "") {
        arr = arr.filter((value) => {
          let author = value.author;
          // eslint-disable-next-line no-unused-vars
          let authorReverse = value.author.split(" ").reverse().join(" ");
          if (author.toLowerCase().startsWith(this.selectAuthor)|| authorReverse.toLowerCase().startsWith(this.selectAuthor)) return true;
        });
      }
      return arr;
    },
  },
  methods: {
    selectedGenres(event) {
      console.log(event);
      this.selectGenre = event;
    },
    selectedAuthor(text) {
      this.selectAuthor = text.trim().toLowerCase();
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  .row {
    .cards {
      margin: 1rem;
    }
  }
}
</style>
