<template>
  <div class="wrapper">
  <Header :query="query"/>
    <h1 class="text-center">Here are some of my favorite movies!</h1>
    <section class="container">
      <Card
        v-for="movie of movieList"
        :key="movie.id"
        :movie="movie"
      />
    </section>
  </div>
</template>

<script>
import Card from '~/components/Card.vue';
import axios from 'axios';

export default {
  components: {
    Card
  },
  data() {
    return {
      movieList: [
        {original_title: 	"Spider-Man: No Way Home", poster_path: "/1g0dhYtq4irTY1GPXvft6k4YLjm.jpg", release_date: "2021-12-15"},
        {original_title: 	"Spider-Man", poster_path: "/gh4cZbhZxyTbgxQPxD0dOudNPTn.jpg", release_date: "2002-05-01"},
        {original_title: "Rush Hour", poster_path: "/we7wOLVFgxhzLzUt0qNe50xdIQZ.jpg", release_date: "1998-09-18"},
        {original_title: "Doctor Strange in the Multiverse of Madness", poster_path: "/9Gtg2DzBhmYamXBS1hKAhiwbBKS.jpg", release_date: "2022-05-04"}
      ]
    }
  },
  head() {
    return {
      title: 'Favorites',
      meta: [
        {
          hid: "A list of recent favorite movies of the developer",
        }
      ]
    }
  }
}
</script>



<!-- This is important https://image.tmdb.org/t/p/w500 for cards, it took me a while to figure out how to do this, but I got it -->





<style>
.container {
  min-height: 100vh;
  max-width: 1200px;
  margin: auto;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  text-align: center;
}

</style>
