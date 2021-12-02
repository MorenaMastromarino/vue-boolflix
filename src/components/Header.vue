<template>
  <header>
    <h2>boolflix</h2>
    <div>
      <input
        v-model="movieToSearch" 
        @keyup.enter="searchMovie"
        type="text"
      >
      <button @click="searchMovie">Cerca</button>
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
  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 70px;
    background-color: black;
    h2 {
      text-transform: uppercase;
      color: red;
    }
  }
</style>