<template>
  <span>
    <h2>This is our Pokedex HEADER component!</h2>
    <Sort :type="type"/>
    <SearchFilter/>
  </span>
</template>

<script>
import Sort from './Sort.vue';
import SearchFilter from './SearchFilter.vue';

export default {
  props: ['type'],
  
  components: {
    Sort,
    SearchFilter
  }
};

</script>

<style>


</style>
