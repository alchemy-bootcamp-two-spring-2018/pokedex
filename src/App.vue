<template>
  <div id="app">
    App area
    <section class="header">
      <HeaderArea/>
    </section>
    <section class="results">
      <ResultsViewer :pokemonList="pokemonList"/>
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
      pokemonList: pokemonList
    }
  },
      components: {
      HeaderArea,
      ResultsViewer
    }
}

</script>

<style>

</style>
