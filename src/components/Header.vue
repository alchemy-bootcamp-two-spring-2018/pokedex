<template>
  <div>
    <h1>Pokedex</h1>
    <filterArea :pokemontype="filterOptions"/>

  </div>
</template>

<script>
  import filterArea from "./Filter.vue";
  export default {
    components: {
      filterArea
    },
    props: ['pokemonList']
  };
</script>