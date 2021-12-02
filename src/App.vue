<template>
  <div>
    <Header @sendSearchMovie="getMovies"/>
    <Main :movies="movies"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';

import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main,

  },
  data(){
    return{
      movies: [],
      apiUrl: 'https://api.themoviedb.org/3/search/movie',
      apiParams: {
        api_key: '4c65b157b05d7ca88b4ecc360dee1a81',
        language: 'it-IT',
        query: '',
      }
    }
  },
  methods: {
    getApi(){
      axios.get(this.apiUrl, {params: this.apiParams})      
      .then(response => {
        this.movies = response.data.results;
        console.log('movies in app', this.movies);
      })
      .catch(error => {
        console.log(error);
      })
    },

    getMovies(movieToSearch){
      this.apiParams.query = movieToSearch;
      this.getApi();
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/generals.scss';

</style>

