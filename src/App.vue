<template>
  <div id="app">

    <h1>Pokedex</h1>
    <PokeHeader :filtered="filter" :sorted="sort"/>
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
        type: ''
      },
      sort: {
        sortBy: ''
      }
    }

  },
  computed: {
    filteredPokemon() {
      return this.pokemonList
        .filter(pokemon => pokemon.type_1 === this.filter.type)
      },
    sortedFilteredPokemon() {
      if(!this.filteredPokemon) return [];
      if(this.sort.sortBy==='attack') {
        return this.filteredPokemon
          .slice()
          .sort((a,b) => a.attack - b.attack)
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
  background: white;
  height: 803px;
  font-family: 'Sunflower', sans-serif;
}

h1, h2, h3, p {
  margin: 0px;
}


</style>
