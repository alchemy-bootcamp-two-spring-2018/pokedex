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
  display: flex;
  flex-wrap: wrap;
  align-content: center;
  text-align: center;
  height: 600px;
  overflow: auto;
}
</style>