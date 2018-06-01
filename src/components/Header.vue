<template>
  <div>
    <h1>This is a Header</h1>
    <section class="filter">
      <pokemonFilter :filterSelection="filter"/>
     
    </section>

    <section class="sort">
      <Sort />
    </section>
    
  </div>
</template>

<script>

import PokemonFilter from './Filter.vue'
import Sort from './Sort.vue'

export default {
  props: ['filter', 'sort'],

  components: {
    PokemonFilter,
    Sort
  }
};

</script>

<style>

</style>