<template>
  <div> 
  <div class="tile-area"> 
    <Tile
      v-for="pokemon in pokemonList"
      @select="$emit('select', $event)"
      :key="pokemon.pokemon"
      :pokemon="pokemon"
      :selected="selected"
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
    props: ['pokemonList', 'selected']
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