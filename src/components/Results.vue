<template>
  <div>
    <h1> If this is displaying, Results is loading</h1>
    
    <Tile 
      v-for="pokemonEach in pokemonList"
      :key="pokemonEach.id"
      :pokemon="pokemonEach"
    />

    <p> Name: {{ filter }} </p>

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
