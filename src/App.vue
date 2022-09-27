<template>
  <div class="" id="app">
      
      <header-section/>

      <loader-component v-if="data.length == 0"/>
      <content-section v-cloak v-else :data="data"/>
  </div>
</template>

<script>
import ContentSection from './components/contentSection.vue'
import HeaderSection from './components/headerSection.vue'
import LoaderComponent from './components/loaderComponent.vue';
const axios = require("axios").default;
export default {
  name: 'App',
  components: {
    HeaderSection,
    ContentSection,
    LoaderComponent,

  },
  data() {
    return {
     data: []
    }
  },
    created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((response) => {
      console.log("OK")
      this.data = [...response.data.response];
    });
  },
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "@/variables";
body {
  background-color: $primary-color;

}

</style>
