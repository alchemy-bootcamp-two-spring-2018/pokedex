<template>

<div id = "header">
    <h1 class="main">Pokedex</h1>

    <section class="filter">
      <PokemonFilter :filterSelection="filter"/>
    </section>

    <section class="sort">
      <Sort :sort="sort"/>
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
h1.main {
  text-align: center;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 3em;
}
#header {
  background-color: rgb(150, 187, 196);
  padding-top: 10px;
  padding-bottom: 10px;

}

</style>