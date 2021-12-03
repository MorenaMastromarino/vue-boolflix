<template>
  <div class="card">

    <p>
      <strong>Titolo: </strong>
      {{item.title || item.name}}
    </p>

    <img :src="`https://image.tmdb.org/t/p/w342${item.poster_path}`" :alt="item.title || item.name">

    <p>
      <strong>Titolo originale: </strong>
      {{item.original_title || item.original_name}}
    </p>

    <div class="language">
      <strong>Lingua originale: </strong>

      <img v-if="item.original_language === 'en'" src="../assets/img/en.png" alt="english flag">

      <img v-else-if="item.original_language === 'it'" src="../assets/img/it.png" alt="italian flag">

      <span v-else>{{item.original_language}}</span>          
    </div>

    <p>
      <strong>Voto: </strong>
      
      <i 
        v-for="(star, index) in getStars(item)" 
        :key="'star'+index" 
        class="fas fa-star">
      </i>

      <i 
        v-for="(emptyStar, index) in (5 - getStars(item))" 
        :key="'emprtyStar'+index" 
        class="far fa-star">
      </i>


    </p>  

  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    item: Object,
  },
  methods: {
    getStars(item){ 
      return Math.ceil(item.vote_average / 2);
    }
  }

}
</script>

<style lang="scss" scoped>
@import url('~@fortawesome/fontawesome-free/css/all.min.css');

.card{
  margin: 10px;
}
.language img {
  width: 30px;
}
</style>