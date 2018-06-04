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
      pokemonTypes: [],
      pokemonList: pokemonList,
      filter: {
        type: [],
        hp: ''
      },
      sort: {
        sortBy: 'id'
      }
    }
  },

  computed: {
    types() {
      this.pokemonList.forEach((pokemon) => this.pokemonTypes.push(pokemon.type_1));
      return Array.from(new Set(this.pokemonTypes));
    },

    filteredPokemon() {
        return this.pokemonList.filter(pokemon => {
          return (!this.filter.type[0] || (pokemon.type_1 === this.filter.type[0] || pokemon.type_2 === this.filter.type[0]))
            && (!this.filter.type[1] || (pokemon.type_1 === this.filter.type[1] || pokemon.type_2 === this.filter.type[1]))
            && (this.filter.hp < 0 || pokemon.hp > this.filter.hp)
        })

      },

    sortedFilteredPokemon() {
      return this.filteredPokemon
        .slice()
        .sort((a, b) => {
          if(a[this.sort.sortBy] < b[this.sort.sortBy]) {
            return -1;
          }
          if(a[this.sort.sortBy] > b[this.sort.sortBy]) {
            return 1;
          }
          return 0;
        })
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
  font-family: 'Sunflower', sans-serif;
}

h1, h2, h3, p {
  margin: 0px;
}


</style>
