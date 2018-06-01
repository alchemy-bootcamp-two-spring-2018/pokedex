<template>
  <div id="app">
    <section class="header">
      <HeaderArea 
        :pokemonType="pokemonList"
         :filter="filter"
      />
    </section>
    <section class="results">
      <ResultsViewer :pokemonList="filterPokemon"/>
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
        defense: '',
      }
    }

  },
      components: {
      HeaderArea,
      ResultsViewer
    },
  computed: {
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
