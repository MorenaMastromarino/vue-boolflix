<template>
  <main>
    <h2>Film</h2>
    <div class="movies-list">

      <Card 
        v-for="movie in movies"
        :key="movie.id" 
        :movie="movie"
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