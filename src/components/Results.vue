<template>
  <div>
    <h1>VIEW YOUR POKEMON</h1>
    
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

<style scoped>
h1 {
  text-align: center;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 2em;
}

</style>
