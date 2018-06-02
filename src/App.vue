<template>
  <div id="app">
    <title>Pokedex</title>
    
    <section class="header">
      <PokedexHeader
      :type="type"
      :filter="filter"
      :sort="sort"
      />
    </section>

    <section class="results">
      <PokedexResults
      :pokemonProp="pokemonList"
      :getFiltered="getFiltered"
      :finalSort="finalSort"
      />
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

      filter: {
        type: 'All',
        attack: ''
      },

      sort: {
        prop: 'pokemon'
      },

      type: [
        'all',
        'grass',
        'fire',
        'water',
        'bug',
        'normal',
        'poison',
        'electric',
        'ground',
        'fairy',
        'fighting',
        'psychic',
        'rock',
        'ghost',
        'ice',
        'dragon',
        'dark',
        'steel',
        'flying'
      ]
    };
  },

  components: {
    PokedexHeader,
    PokedexResults
  },

  computed: {

    finalSort() {
      return this.getFiltered.slice().sort((a, b) => {
        const x = a[this.sort.prop];
        const y = b[this.sort.prop];
        if (x < y) {return -1;}
        if (x > y) {return 1;}
        return 0;
      })
    },

    getFiltered() {
      return this.pokemonList.filter(pokemon => {
        return (this.filter.type.toLowerCase() === 'all' || pokemon.type_1 === this.filter.type.toLowerCase())
        && (this.filter.attack < 0 || pokemon.attack > this.filter.attack)
      });
    },
  }

};
</script>


<style>

</style>
