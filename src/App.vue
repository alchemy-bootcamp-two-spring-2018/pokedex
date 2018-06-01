<template>
  <div id="app">
  
    <title>Pokedex</title>
    <h1>This is our pokedex APP!</h1>
    <section class="header">
      <PokedexHeader :type="type"/>
    </section>

    <section class="results">
      <PokedexResults :pokemonProp="pokemonList"/>
    </section>
    
  </div>
</template>


<script>


import PokedexHeader from './components/PokedexHeader.vue';
import PokedexResults from './components/PokedexResults.vue';
import pokemon from '../pokemon.js';

export default {
  data() {
    return {
      pokemonList: pokemon,
      type: [
        'Grass',
        'Fire',
        'Water',
        'Bug',
        'Normal',
        'Poison',
        'Electric',
        'Ground',
        'Fairy',
        'Fighting',
        'Psychic',
        'Rock',
        'Ghost',
        'Ice',
        'Dragon',
        'Dark',
        'Steel',
        'Flying'
      ]
    };
  },

  components: {
    PokedexHeader,
    PokedexResults
  }

};

</script>


<style>

</style>
