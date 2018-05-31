<template>
  <div id="app">
    <h1>Poke Dex</h1>
    <section id="header-filter">
      <pokeFilter
      v-bind:filter="filter"
      />
    </section>
    <section id="pokemon-display">
      <tile/>
    </section>
  </div>
</template>

<script>
import tile from './components/tile.vue'
import pokeFilter from './components/pokeFilter.vue'

export default {
  name: 'app',
  data(){
    return {
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
