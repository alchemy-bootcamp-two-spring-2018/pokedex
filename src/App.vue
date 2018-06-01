<template>
  <div id="app">

    <section>
      <Header :filter="filter" :sort="sort"/>
    </section>

    <section>
      <Results :pokemonList="pokeType" :filter="filter.type"/>   
    </section>

  </div>
</template>

<script>

import Header from './components/Header.vue';
import Results from './components/Results.vue';
import pokemon from '../pokemon.js';

export default {
  data() {
    return {
      pokeList: pokemon,

      filter: {type: ''},

      sort: {name: ''}
    };
  },

  computed: {
    pokeType() {
      if(!this.filter.type) return [];
      return this.pokeList.filter(pokemon => pokemon.type_1 === this.filter.type);

    }
  },

  components: {
    Header,
    Results
  }
};

</script>

<style>

</style>
