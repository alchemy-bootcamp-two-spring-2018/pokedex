<template>
  <div>
    <h1>Pokedex</h1>
    <div id="options">
      <filterArea :filter="filter"/>
      <sortArea :sort="sort"/>
    </div>
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
<style>
#options {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items:center;

}
</style>