<template>
  <div id="app">

    <section>
      <Header :filter="filter" :sort="sort"/>
    </section>

    <section>
      <Results :pokemonList="filtered" :filter="filter.type"/>   
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

      filter: {
        type: '',
        hp: ''
      },

      sort: {name: ''}
    };
  },

  computed: {
    filtered() {
      return this.pokeList.filter(pokemon => {
        if(this.filter.type === 'All') {
          return (this.pokeList)
          && (pokemon.hp === '' || pokemon.hp >= this.filter.hp);
        }
        return (pokemon.type_1 === '' || pokemon.type_1 === this.filter.type)
        && (pokemon.hp === '' || pokemon.hp >= this.filter.hp)
      });
    },
  },

  components: {
    Header,
    Results
  }
};

</script>

<style>

</style>
