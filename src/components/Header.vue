<template>
  <div>
    <h1>Pokedex</h1>
    <filterArea :filter="filter"/>
    <sortArea :sort="sort"/>
  </div>
</template>

<script>
  import filterArea from "./Filter.vue";
  import sortArea from "./Sort.vue";
  export default {
    components: {
      filterArea,
      sortArea
    },
    props: ['filter', 'sort']
  };
</script>