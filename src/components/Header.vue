<template>
  <div>
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
    props: ['filter', 'sort', 'pokemonType']
  };
</script>
<style>
#options {
  display: flex;
  flex-direction: row;
  margin-top: 35px;
  margin-left: 100px;
  
}
</style>