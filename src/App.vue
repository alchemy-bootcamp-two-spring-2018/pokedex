<template>
  <div id="app">
    <poke-header 
      :pokeList="remDupes"
      @change="filterTypes"
      @name="sortName"
      @type="sortType"
      @all="displayAll"
    />
    <poke-results
      :banana="filteredList"
    />
  </div>
</template>

<script>
import PokeHeader from './components/PokeHeader.vue'
import PokeResults from './components/PokeResults.vue'
import pokeList from './assets/pokemon.js'

export default {
  name: 'app',
  data() {
    return {
      pokeList: pokeList,
      filteredList: ''
    }
  },
  components: {
    PokeHeader,
    PokeResults
  },
  methods: {
    filterTypes(pokeType) {
      this.filteredList = pokeList.filter(a => a.type_1 === pokeType);
    },
    displayAll() {
      this.filteredList = this.pokeList;
    },
    sortName() {
      // Compare strings
      this.filteredList.sort((a, b) => ('' + a.pokemon).localeCompare(b.pokemon));
    },
    sortType() {
      // Compare strings
      this.filteredList.sort((a, b) => ('' + a.pokemon).localeCompare(b.pokemon));
    }
  },
  computed: {
    remDupes() {
      return this.pokeList.filter((obj, pos, arr) => {
          return this.pokeList.map(mapObj => mapObj.type_1).indexOf(obj.type_1) === pos;
      });
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
