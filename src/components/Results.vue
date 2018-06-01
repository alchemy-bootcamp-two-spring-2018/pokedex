<template>
  <div>
    <h1> If this is displaying, Results is loading</h1>
    
    <Tile 
      v-for="pokemonEach in pokemonList"
      :key="pokemonEach.id"
      :pokemon="pokemonEach"
    />
  </div>
</template>

<script>
 import Tile from './Tile.vue'


export default {

  components: {
    Tile
  },

  props: ['pokemonList']
}

</script>

<style>

</style>
