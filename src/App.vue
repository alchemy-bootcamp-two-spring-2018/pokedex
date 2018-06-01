<template>
  <div id="app">

    <PokeHeader :filtered="filter" :types="types" :sorted="sort"/>
    <Results :pokeList="sortedFilteredPokemon"/>
  </div>
</template>

<script>
import PokeHeader from './components/PokeHeader';
import Results from './components/Results';
import pokemonList from '../pokemon.js';

export default {
  data() {
    return {
      pokemonList: pokemonList,
      filter: {
        type: '',
        pokemonTypes: []
      },
      sort: {
        sortBy: ''
      }
    }
  },

  computed: {
    types() {
      this.pokemonList.forEach((pokemon) => this.filter.pokemonTypes.push(pokemon.type_1));
      return Array.from(new Set(this.filter.pokemonTypes));
    },

    filteredPokemon() {
      if(!this.filter.type) return this.pokemonList;
      return this.pokemonList
        .filter(pokemon => pokemon.type_1 === this.filter.type || pokemon.type_2 === this.filter.type)
      },

    sortedFilteredPokemon() {
      if(this.sort.sortBy==='id') {
        return this.filteredPokemon
          .slice()
          .sort((a,b) => a.id - b.id)
      }
      else {
        return this.filteredPokemon
          .slice()
          .sort((a,b) => {
            if (a.pokemon < b.pokemon) {
              return -1;
            }
            if (a.pokemon > b.pokemon) {
              return 1;
            }
          })
      }
    }
  },
  components: {
    PokeHeader,
    Results
  }
}
</script>

<style>
#app {
  background: #fa0505;
  height: 803px;
  font-family: 'Sunflower', sans-serif;
}

h1, h2, h3, p {
  margin: 0px;
}


</style>
