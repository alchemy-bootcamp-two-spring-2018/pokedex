<template>
  <span>
    <h2>This is our Pokedex HEADER component!</h2>
    <Sort
    :sort="sort"
    />
    <SearchFilter
    :type="type"
    :filter="filter"
    />
  </span>
</template>

<script>
import Sort from './Sort.vue';
import SearchFilter from './SearchFilter.vue';

export default {
  props: ['type', 'filter', 'sort'],
  
  components: {
    Sort,
    SearchFilter,
  }
};

</script>

<style>


</style>
