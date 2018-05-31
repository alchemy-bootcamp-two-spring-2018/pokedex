<template>
  <div id="app">
    <h1>Poke Dex</h1>
    <section id="header-filter">
    </section>
      <pokeFilter
      v-bind:filter="filter"
      />
    <section id="pokemon-display">
      <tile 
        v-bind:pokeTiles= "list"
      />
    </section>
  </div>
</template>

<script>
import pokeDex from './pokemon.js'
import tile from './components/tile.vue'
import pokeFilter from './components/pokeFilter.vue'

export default {
  name: 'app',
  data(){
    return {
      list: pokeDex,
      filter: {
        type: '',
      }
    }
  },
  components: {
    tile,
    pokeFilter
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
