<template>
  <div class="d-flex flex-column text-center">
    <img :src="img" alt="">
    <h2 class="mt-3">{{title}}</h2>
    <p>{{author}}</p>
    <p>{{year}}</p>
  </div>
</template>

<script>
export default {

    props: {
        title: String,
        author: String,
        year: String,
        img: String
    }

}
</script>


<style lang="scss" scoped>
@import "@/variables.scss";

div {
    background-color: $secondary-color;
    padding: 1rem;
    img {
        width: 100%;
    }
    h2 {
        color: white;
        text-transform: uppercase;
        font-size: 1.5rem;
    }
    p {
        padding: 0;
        margin: 0;
        color: $text-secondary;
        text-transform: capitalize;
    }
}


</style>