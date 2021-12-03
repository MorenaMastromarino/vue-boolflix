<template>
  <main>

    <!-- film -->
    <h2 v-if="movies.length > 0">Film</h2>
    <div class="movies-list">

      <Card 
        v-for="movie in movies"
        :key="movie.id" 
        :item="movie"
      />

    </div>

    <!-- serie -->
    <h2 v-if="series.length > 0">Serie TV</h2>
    <div class="movies-list">

      <Card 
        v-for="serie in series"
        :key="serie.id" 
        :item="serie"
      />

    </div>

         
  </main>
</template>

<script>
import Card from './Card.vue';

export default {
  name: 'Main',
  props: {
    movies: Array,
    series: Array,
  },
  components: {
    Card,
  }
}
</script>

<style lang="scss" scoped>
.movies-list {
  display: flex;
}
</style>