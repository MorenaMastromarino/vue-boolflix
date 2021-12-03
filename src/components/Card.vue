<template>
  <div class="card">

    <p>
      <strong>Titolo: </strong>
      {{item.title || item.name}}
    </p>

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
      {{item.vote_average}}
    </p>  

  </div>
</template>

<script>
export default {
name: 'Card',
props: {
  item: Object,
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