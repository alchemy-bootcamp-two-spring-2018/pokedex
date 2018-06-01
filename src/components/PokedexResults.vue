<template>
  <span>
    <h2>This is our Pokedex RESULTS!</h2>
    <Tile :pokemonProp="pokemonProp"/>

  </span>
</template>

<script>
import Tile from './Tile.vue';

export default {

  props: ['pokemonProp'],

  components: {
    Tile
  }
};

</script>


<style>

</style>