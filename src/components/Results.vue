<template>
  <div>
    <h1> If this is displaying, Results is loading</h1>
    
    <Tile 
      v-for="eachPokemon in pokemonList"
      :key="eachPokemon.id"
      :pokemon="eachPokemon"
    />

  </div>
</template>

<script>
 import Tile from './Tile.vue'


export default {

  components: {
    Tile
  },

  props: ['pokemonList', 'filter']
}

</script>

<style>

</style>
