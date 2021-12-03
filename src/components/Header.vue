<template>
  <header class="d-flex align-items-center justify-content-between">
    <h2 class="mb-0 text-uppercase">boolflix</h2>
    <div class="d-flex">
      <input
        v-model="movieToSearch" 
        @keyup.enter="searchMovie"
        type="text"
        class="form-control"
        placeholder="Cerca un film o una serie tv"
      >
      <button 
        @click="searchMovie"
        type="button" 
        class="btn btn-outline-danger">
        Cerca
      </button>
      
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data(){
    return{
      movieToSearch: '',
    }
  },
  methods: {
    searchMovie(){
      this.$emit('sendSearchMovie', this.movieToSearch);
      this.movieToSearch = '';
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/vars.scss';

  header {
    height: 80px;
    padding: 0 20px;
    background-color: darken($primary-color, 20%);
    h2 {
      font-size: 45px;
      color: $logo-color;
      cursor: pointer;
    }
    button {
      margin-left: 10px !important;
      color: $logo-color;
      border-color: $logo-color;
      &:hover {
        background-color: $logo-color;
      }
    }
  }
</style>