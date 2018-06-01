<template>
  <div>
    <h1>Results</h1>
    {{ pokemonList.length }}
  <div class="tile-area"> 
    <Tile
      v-for="pokemon in pokemonList"
      :key="pokemon.pokemon"
      :pokemon="pokemon"
    />
  </div>
  </div>
</template>

<script>
  import Tile from './Tile.vue';
  
  export default {
    components: {
      Tile
    },
    props: ['pokemonList']
  }
</script>

<style>
.tile-area {

  align-content: center;
  text-align: center;
  height: 600px;
  overflow: auto;
}
</style>