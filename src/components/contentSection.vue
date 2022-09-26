<template>
  <div class="container mt-5">
    <div class="row">
      <card-component
        class="col-2 cards"
        v-for="(poster, index) in posters"
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
const axios = require("axios").default;
export default {
  components: { cardComponent },

  data() {
    return {
      posters: [],
    };
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((response) => {
      this.posters = [...response.data.response];
    });
  },
};
</script>

<style lang="scss" scoped>
.container {
    .row {
        .cards{
            margin: 1rem
        }
    }
}


</style>
