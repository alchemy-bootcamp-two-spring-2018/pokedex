<template>
  <div>
    <h1>Results</h1>
  <div class="tile-area"> 
    <Tiles v-for="pokemonTile in pokemonList"
      :key="pokemonTile"
      :pokemonTile="pokemonTile"
    />
  </div>
  </div>
</template>

<script>
  import Tiles from './Tile.vue';
  
  export default {
    components: {
      Tiles
    },
    props: ['pokemonList']
  }
</script>

<style>
.tile-area {
  height: 500px;
  overflow: auto;
}
</style>