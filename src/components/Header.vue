<template>
  <div>
    <h1>This is a Header</h1>
    <section class="filter">
      <input type="checkbox" value="type">Type</input>
      <input type="checkbox" value="HP">HP</input>
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

import Filter from './Filter.vue'
import Sort from './Sort.vue'

export default {
  props: [
    'Filter',
    'Sort'
  ]
};

</script>

<style>

</style>