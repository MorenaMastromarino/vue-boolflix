<template>
  <div>
    <Header/>
    <Main/>
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
  methods: {
    getApi(){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=4c65b157b05d7ca88b4ecc360dee1a81&language=it-IT&query=ritorno+al+futuro')      
      .then(response => {
        console.log(response.data.results);
      })
      .catch(error => {
        console.log(error);
      })
    }
  },
  mounted(){
    this.getApi();
  }
}
</script>

<style lang="scss">
@import './assets/style/generals.scss';

</style>

