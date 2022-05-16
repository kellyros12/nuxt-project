<template>
  <div class="wrapper">
  <Header :query="query"/>
    <div>
      <input v-on:keydown.enter="getData" v-model="query" class="searchbar" placeholder="Enter your favorite actor or actress and press enter!">
    </div>
    <section class="container" v-if="movies">
      <Card
        v-for="movie of movies"
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
    loading: null,
    movies: null,
    errored: false,
    query: ''
    }
  },
  methods: {
    getData() {
      axios
      .get(`https://api.themoviedb.org/3/search/person?api_key=edafdbb27f449121ff42f0328be88798&language=en-US&query=${this.query}&include_adult=false`)
      .then(response => (this.movies = response.data.results[0].known_for))
      .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
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

.searchbar {
  width: 75%;
  margin-top: 5em;
  margin-left: 12.5%;

}
</style>
