<template>
  <div class="card">
    <p><strong>Titolo: </strong>{{movie.title}}</p>
        <p><strong>Titolo originale: </strong>{{movie.original_title}}</p>
        <div class="language">
          <strong>Lingua originale: </strong>
          <img v-if="movie.original_language === 'en'" src="../assets/img/en.png" alt="english flag">
          <img v-else-if="movie.original_language === 'it'" src="../assets/img/it.png" alt="italian flag">
          <span v-else>{{movie.original_language}}</span>          
        </div>
        <p><strong>Voto: </strong>{{movie.vote_average}}</p>     
  </div>
</template>

<script>
export default {
name: 'Card',
props: {
  movie: Object,
}

}
</script>

<style lang="scss" scoped>
.card{
  margin: 10px;
}
.language img {
  width: 30px;
}
</style>