<template>
  <span>
    <h2>This is our Pokedex RESULTS component!</h2>
    <Tile
    :pokemonProp="pokemonProp"
    :getFiltered="getFiltered"
    :sortedByName="sortedByName"
    :sortedByType="sortedByType"
    />

  </span>
</template>

<script>
import Tile from './Tile.vue';

export default {

  props: ['pokemonProp', 'getFiltered', 'sortedByName', 'sortedByType'],

  components: {
    Tile
  }
};

</script>


<style>

</style>