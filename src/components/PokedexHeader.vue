<template>
  <span>
    <h2>This is our Pokedex HEADER!</h2>
    <Sort/>
    <SearchFilter/>
  </span>
</template>

<script>
import Sort from './Sort.vue';
import SearchFilter from './SearchFilter.vue';

export default {

  
  components: {
    Sort,
    SearchFilter
  }
};

</script>

<style>


</style>
