<template>
  <div class="container mt-5">
    <div class="row justify-content-center">
      <card-component
        class="col-lg-2 col-md-3 col-sm-8 col-12 cards"
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
export default {
  components: { cardComponent },

  data() {
    return {
      posters: [],
    };
  },
  props: {
    data: Array
  },
  mounted() {
    this.posters = this.data
  }
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
