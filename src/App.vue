<template>
  <div id="app">
  
    <title>Pokedex</title>
    <h1>This is our pokedex!</h1>
    <section class="header">
      <PokedexHeader/>
    </section>

    <section class="results">
      <PokedexResults/>
    </section>
    
  </div>
</template>


<script>

import pokemon from '../pokemon.js';
import PokedexHeader from './components/PokedexHeader.vue';
import PokedexResults from './components/PokedexResults.vue';

export default {

  data() {
    return {
      list: pokemon
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
