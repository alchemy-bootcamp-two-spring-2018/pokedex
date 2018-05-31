<template>
  <div id="app">

    <section>
      <Header />
    </section>

    <section>
      <Results />
      
        </section>

  </div>
</template>

<script>

import Header from './components/Header.vue';
import Results from './components/Results.vue';
import Pokemon from '../pokemon.js';

export default {
  data (){
    return {
      list: Pokemon
    }
  },
  components: {
    Header,
    Results
  }
}
</script>

<style>

</style>
