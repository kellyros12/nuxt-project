<script>
export default {
  props: {
    movie: Object
  }
}
</script>


<template>
  <article class="card">
    <img :src="`https://image.tmdb.org/t/p/w500${this.movie.poster_path}`" :alt="movie.original_title" class="card__img">
    <h2 class="card__title">{{ movie.original_title }}</h2>
    <p class="card__copy">Release: {{ movie.release_date }}</p>
  </article>
</template>

<style>
.card {
  margin: 1rem;
  border: 1px solid #000;
  padding: 1.5rem;
  width: 300px;
  height: 550px;

  &__img {
    display: block;
    margin-bottom: 1rem;
  }
  &__title {
    font-size: 1rem;
    margin-bottom: .25rem;
  }
  &__copy {
    font-size: 0.875rem;
  }
}
</style>
