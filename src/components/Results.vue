<template>
  <div> 
  <div class="tile-area"> 
    <Tile
      v-on:select="$emit('select', pokemon)"
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
    props: ['pokemonList', 'select']
  }
</script>

<style>
.tile-area {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  text-align: center;
  height: 36.5em;
  overflow: auto;
  width: 63em;
  margin-left: -30px;
}
</style>