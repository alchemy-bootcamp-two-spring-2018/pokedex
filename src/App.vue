<template>
  <div id="app">
    <section class="header">
      <HeaderArea 
        :pokemonType="pokemonList"
         :filter="filter"
         :sort="sort"
      />
    </section>
    <section class="results">
      <ResultsViewer 
      :pokemonList="sorted"/>
    
    </section>
  </div>
</template>

<script>
import HeaderArea from './components/Header.vue';
import ResultsViewer from './components/Results.vue';
import pokemonList from './pokemon.js';
export default {
  data() {
    return {
      pokemonList: pokemonList,
      filter: {
        type: '',
        defense: ''
      },
      sort: {
        sortBy: ''
      }
    }
  },
    components: {
    HeaderArea,
    ResultsViewer
    },
  computed: {
      sorted() {
        if(this.sort.sortBy === 'defense') {
          return this.filterPokemon.slice().sort((a, b) => b.defense - a.defense);
        }
        else if(this.sort.sortBy === 'attack') {
          return this.filterPokemon.slice().sort((a, b) => b.attack - a.attack);
        }
        else {
          return this.filterPokemon.slice().sort((a, b) => a.id - b.id);
        }
    },
    filterPokemon() {
      const{type, defense} = this.filter;
      return pokemonList.filter(pokemon => {
        return (type === 'all' || pokemon.type_1 === type || pokemon.type_2 === type)
        &&(defense < 0 || pokemon.defense > defense);
      });
    }
  }
}


</script>

<style scoped>
  #app {
    text-align: center;
    background: rgba(220, 20, 20, 0.918);
    margin: -20px;
  }
</style>
