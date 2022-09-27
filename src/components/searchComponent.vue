<template>
  <div class="row m-3 justify-content-between">
    <div class="col-3">
      <label for="genre" class="form-label">GENRE</label>
      <select class="form-control" name="genre" id="" @change.prevent="getSelectedGenre">
        <option value="">Select...</option>
        <option
          v-for="(genre, index) in data"
          :key="index"
          :value="genre"
          :selected="genre == selected"
        >
          {{ genre }}
        </option>
      </select>
    </div>
    <div class="col-4 text-end">
      <div class="mb-3">
        <label for="" class="form-label">AUTHOR</label>
        <input type="text" class="form-control" name="" id="" aria-describedby="helpId" placeholder="FrancoDJ" v-model="text" @keyup.capture="getSelectedAuthor">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: this.genres,
      selected: "",
      text: ""
    };
  },

  props: {
    genres: Array,
  },
  methods: {
    getSelectedGenre(event) {
      this.$emit("searchGenre", event.target.value);
    },
    getSelectedAuthor() {
      this.$emit("searchAuthor", this.text);
    }
  },
};
</script>

<style lang="scss" scoped>
@import "@/variables.scss";
div.row {
  color: white;
}
</style>
