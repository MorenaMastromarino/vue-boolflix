<template>
  <header>
    <h2>boolflix</h2>
    <div>
      <input type="text">
      <button>Cerca</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',

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