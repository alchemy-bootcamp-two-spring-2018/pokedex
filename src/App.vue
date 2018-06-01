<template>
  <div id="app">

    <section>
      <Header :filter="filter" :sort="sort"/>
    </section>

    <section>
      <Results :pokemonList="list" :filter="filter.type"/>   
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

      sort: { name: ''}
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
