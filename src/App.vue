<template>
  <div class="" id="app">
      <header-section/>
      <content-section/>
  </div>
</template>

<script>
import ContentSection from './components/contentSection.vue'
import HeaderSection from './components/headerSection.vue'

export default {
  name: 'App',
  components: {
    HeaderSection,
    ContentSection
  }
}
</script>

<style lang="scss">
@import "/node_modules/bootstrap/scss/bootstrap.scss";
@import "@/variables";
body {
  background-color: $primary-color;
  
}

</style>
