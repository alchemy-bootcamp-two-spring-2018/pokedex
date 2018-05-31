<template>
  <div id="app">
    <poke-header 
      :pokeList="pokeList"
    />
    <poke-results />
  </div>
</template>

<script>
import PokeHeader from './components/PokeHeader.vue'
import PokeResults from './components/PokeResults.vue'
import pokeList from './assets/pokemon.js'

export default {
  name: 'app',
  components: {
    PokeHeader,
    PokeResults
  },
  data() {
    return {
      pokeList: pokeList
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
