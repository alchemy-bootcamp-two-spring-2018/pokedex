<template>
  <div id="app">
  
    <title>Pokedex</title>
    <h1>This is our pokedex APP!</h1>
    <section class="header">
      <PokedexHeader
      :type="type"
      :filter="filter"
      />
    </section>

    <section class="results">
      <PokedexResults
      :pokemonProp="pokemonList"
      :getFiltered="getFiltered"
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
        name: ''
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
      let filteredPokemon = [];
      for(let i = 0; i < this.pokemonList.length; i++ ) {
        if(this.filter.type.toLowerCase() == 'all') {
          filteredPokemon.push(this.pokemonList[i]);
        } else if(this.filter.type.toLowerCase() == this.pokemonList[i].type_1 || this.filter.type.toLowerCase() == this.pokemonList[i].type_2) {
          filteredPokemon.push(this.pokemonList[i]);
        }
      }
        return filteredPokemon;
    }
/*     filtered() {
      return pokemonList.filter(pokemon => {
        return (type === 'all' || pokemon.type_1 === type_1)
          && (age === 0 || animal.age > age)
          && (neutered === undefined || animal.neutered === neutered)
      });
    } */
  }

};

</script>


<style>

</style>
