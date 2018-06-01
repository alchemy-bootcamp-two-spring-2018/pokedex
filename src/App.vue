<template>
  <div id="app">

    <section>
      <Header :filter="filter"/>
    </section>

    <section>
      <Results :pokemonList="list"/>
      
    </section>

  </div>
</template>

<script>

import Header from './components/Header.vue';
import Results from './components/Results.vue';
import Pokemon from '../pokemon.js';

export default {
  data() {
    return {
      list: Pokemon,

      filter: { type: ''},
    };
  },

  components: {
    Header,
    Results
  }

};



</script>

<style>

</style>
