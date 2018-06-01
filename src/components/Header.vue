<template>
  <div>
    <h1>This is a Header</h1>
    <section class="filter">
      <pokemonFilter />
     
    </section>

    <section class="sort">
      <select>
        <option value="Name">Name</option>
        <option value="Type">Type</option>
      </select>
    </section>
    
  </div>
</template>

<script>

import pokemonFilter from './Filter.vue'
import Sort from './Sort.vue'

export default {
  props: [
    'filter',
    'sort'
  ],
  components: {
    pokemonFilter
  }
};

</script>

<style>

</style>