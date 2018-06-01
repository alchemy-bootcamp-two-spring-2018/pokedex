<template>
  <div id="app">
    <h1>Poke Dex</h1>
    <section id="header-filter">
    </section>
      <pokeFilter
      v-bind:filter="filter"
      @change="updatePokedex"
      />
    <section id="pokemon-display">
      <Results/>
    </section>
  </div>
</template>

<script>
import pokeDex from './pokemon.js'
import Results from './components/Results.vue'
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
    Results,
    pokeFilter
  },
  methods: {
    updatePokedex() {

      // for (let i = 0; i < pokeDex.length; i++) {

      // }
      this.list = pokeDex;
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
