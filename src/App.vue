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
        pokemon: '',
      }
    }

  },
      components: {
      HeaderArea,
      ResultsViewer
    },
  computed: {
    filterPokemon() {
      let filteredPokemon = [];
      console.log(this.filter.type);
      for(let i in this.pokemonList) {
        if(this.filter.type === 'all') {
          filteredPokemon.push(this.pokemonList[i]);
        }
        else if(this.pokemonList[i].type_1 === this.filter.type || this.pokemonList[i].type_2 === this.filter.type){
          filteredPokemon.push(this.pokemonList[i]);
        }
      }
      return filteredPokemon;
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
