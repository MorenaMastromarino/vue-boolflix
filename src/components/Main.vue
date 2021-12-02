<template>
  <main>

    <div v-for="movie in movies" :key="movie.id" class="movie-card">
       <h3>{{movie.title}}</h3>
        <p>{{movie.original_title}}</p>
        <p>{{movie.original_language}}</p>
        <p>{{movie.vote_average}}</p>     
    </div>
         
  </main>
</template>

<script>
export default {
  name: 'Main',
  props: {
    movies: Array,
  }
}
</script>

<style lang="scss" scoped>

</style>