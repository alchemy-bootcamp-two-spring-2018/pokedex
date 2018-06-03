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
        :selected="selected"
        @select="UpdateSelected"
        :pokemonList="sorted"
      />
    </section>
    <section class="viewer">
      <PokemonViewer
        :selectedPokemon="selected"
      />
    </section>
  </div>
</template>

<script>
import HeaderArea from './components/Header.vue';
import ResultsViewer from './components/Results.vue';
import pokemonList from './pokemon.js';
import PokemonViewer from './components/Viewer.vue';
export default {
  data() {
    return {
      pokemonList: pokemonList,
      filter: {
        type: '',
        defense: ''
      },
      sort: {
        sortBy: 'pokemon, attack, defense'
      },
      selected: null
    }
  },
    components: {
    HeaderArea,
    ResultsViewer,
    PokemonViewer
    },
  computed: {
    sorted() {
      if(this.sort.sortBy !== 'pokemon') {
        return this.filterPokemon.slice().sort((a, b) => {
        let pokemonA = a[this.sort.sortBy];
        let pokemonB = b[this.sort.sortBy];
        if(pokemonA === pokemonB) return 0;
        if(pokemonB > pokemonA) return 1;
        return -1;  
      })}
      else {
        return this.filterPokemon.slice().sort((a, b) => {
        let pokemonA = a[this.sort.sortBy];
        let pokemonB = b[this.sort.sortBy];
        if(pokemonA === pokemonB) return 0;
        if(pokemonA > pokemonB) return 1;
        return -1;
      });
    }
    },
    filterPokemon() {
      const{type, defense} = this.filter;
      return pokemonList.filter(pokemon => {
        return (type === 'all' || pokemon.type_1 === type || pokemon.type_2 === type)
        &&(defense < 0 || pokemon.defense >= defense);
      });
    }
  },
  methods: {
    UpdateSelected(pokemon) {
      this.selected = pokemon;
    }
  }
}
</script>
<style>
  html {
    background-image: url('https://orig00.deviantart.net/95ef/f/2016/311/0/f/pokemon_twitch_theme_a_2a_by_masterq2-danm4kn.gif');
    background-repeat: no-repeat; 
    background-size: cover;;
    background-attachment: fixed;
    background-color: rgba(189, 175, 175, 0.555);
    
  }
  #app {
    text-align: center;
    margin: -20px;
    display: grid;

  }
  .results {
    position: absolute;
    top: 90px;
    left: -40px;

  }
  .viewer {
    position: absolute;
    right: 80px;
    top: 50px;
  }
</style>
