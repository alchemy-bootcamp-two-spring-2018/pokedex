<template>
  <div id="app">

    <title>Pokedex</title>
    <h1>This is our pokedex APP!</h1>
    <section class="header">
      <PokedexHeader
      :type="type"
      :filter="filter"
      :sortedByName="sortedByName"
      :sortedByType="sortedByType"
      />
    </section>

    <section class="results">
      <PokedexResults
      :pokemonProp="pokemonList"
      :getFiltered="getFiltered"
      :sortedByName="sortedByName"
      :sortedByType="sortedByType"
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
    
    getFiltered() {
      return this.pokemonList.filter(pokemon => {
        return (this.filter.type.toLowerCase() === 'all' || pokemon.type_1 === this.filter.type.toLowerCase())
        && (this.filter.attack < 0 || pokemon.attack > this.filter.attack)
      });
    },

    sortedByName() {
      return this.getFiltered.slice().sort((a, b) => {
        const x = a.pokemon.toLowerCase();
        const y = b.pokemon.toLowerCase();
        if(x < y) {return -1;}
        if(x > y) {return 1;}
        return 0;
      });
    },

    sortedByType() {
      return this.getFiltered.slice().sort((a, b) => {
        const x = a.type_1.toLowerCase();
        const y = b.type_1.toLowerCase();
        if(x < y) {return -1;}
        if (x > y) {return 1;}
        return 0;
      });
    }
  }


  // sorted() {
  //     return this.filtered.slice().sort((a, b) => { /*...*/ });

};
</script>


<style>

</style>
