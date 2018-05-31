<template>
  <div id="app">
    <h1>Poke Dex</h1>
    <img src='http://assets.pokemon.com/assets/cms2/img/pokedex/full/001.png'>
    <tile/>
  </div>
</template>

<script>
import tile from './components/tile.vue'

export default {
  name: 'app',
  components: {
    tile
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
