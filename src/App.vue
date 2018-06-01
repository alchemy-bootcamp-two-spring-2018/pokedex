<template>
  <div id="app">
  
    <title>Pokedex</title>
    <h1>This is our pokedex!</h1>
    <section class="header">
      <PokedexHeader/>
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
      pokemonList: pokemon
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
