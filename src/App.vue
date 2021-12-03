<template>
  <div>
    <Header @sendSearchMovie="getMovies"/>
    <Main :movies="movies" :series="series"/>
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
      series: [],
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiParams: {
        api_key: '4c65b157b05d7ca88b4ecc360dee1a81',
        language: 'it-IT',
        query: '',
      }
    }
  },
  methods: {
    getApi(){

      // chiamata film
      axios.get(this.apiUrl+'movie', {params: this.apiParams})      
      .then(response => {
        this.movies = response.data.results;        
      })
      .catch(error => {
        console.log(error);
      })

      // chiamata serie
      axios.get(this.apiUrl+'tv', {params: this.apiParams})      
      .then(response => {
        this.series = response.data.results;
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
@import "./assets/style/vars.scss";

</style>

