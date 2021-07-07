<template>
  <div id="app">
    <head>
      <link href="https://fonts.googleapis.com/css?family=Baloo" rel="stylesheet">
    </head>
    <title>Pokedex</title>
    <header>
      <img id="pokemonTitle" src="./assets/pokemon.png" width="400px">
      <br>
      <img src="./assets/pikachu.png" width="130px">
      <img src="./assets/pokeball.png" width="130px">
      <img src="./assets/pokedex.png" width="150px">
    </header>

    <section class="header">
      <PokedexHeader
      :type="type"
      :filter="filter"
      :sort="sort"
      :order="order"
      />
    </section>

    <section class="results">
      <PokedexResults
      :pokemonProp="pokemonList"
      :getFiltered="getFiltered"
      :sortAscending="sortAscending"
      :sortDescending="sortDescending"
      :order="order"
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
        prop: 'id'
      },

      order: {
        prop: 'ascending'
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

    sortAscending() {
      return this.getFiltered.slice().sort((a, b) => {
        const x = a[this.sort.prop];
        const y = b[this.sort.prop];
        if(x < y) {return -1;}
        if(x > y) {return 1;}
        return 0;
      });
    },
    sortDescending() {
      return this.getFiltered.slice().sort((a, b) => {
        const x = a[this.sort.prop];
        const y = b[this.sort.prop];
        if(x > y) {return -1;}
        if(x < y) {return 1;}
        return 0;
      });
    },

    getFiltered() {
      return this.pokemonList.filter(pokemon => {
        return (this.filter.type.toLowerCase() === 'all' || pokemon.type_1 === this.filter.type.toLowerCase() || pokemon.type_2 === this.filter.type.toLowerCase())
        && (this.filter.attack < 0 || pokemon.attack > this.filter.attack);
      });
    },
  }

};
</script>


<style>
#app {
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  background-image: url(./assets/background.jpg);
  background-position: top;
  background-repeat: repeat;
  background-attachment: fixed;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  cursor: url('./assets/cursor_pikachu.png'), pointer;
  min-width: 700px;
}

select {
  cursor: pointer;
}

.header {
  margin: 20px;
  font-size: 24px;
  font-family: 'Baloo', cursive;
}

header img {
  margin: 15px;
}
</style>
