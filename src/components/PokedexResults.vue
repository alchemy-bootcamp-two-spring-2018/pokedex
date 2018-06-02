<template>
  <span>
    
    <h2>This is our Pokedex RESULTS component!</h2>

    <section class="cards" v-if="pokemonProp">
      <span
      class="tile"
      >
        <Tile
        v-for="pokemon in finalSort"
        v-bind:key="pokemon.id"
        :pokemon="pokemon"
        :getFiltered="getFiltered"
        />
      </span>
    </section>
    <p v-else>Select a pokemon to learn more!</p>
  
  </span>
</template>

<script>
import Tile from './Tile.vue';

export default {

  props: ['pokemonProp', 'getFiltered', 'finalSort'],

  components: {
    Tile
  }
};

</script>


<style>

</style>