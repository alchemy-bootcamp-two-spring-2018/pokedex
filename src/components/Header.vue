<template>
  <div>
    <h1>Pokedex</h1>
    <filterArea :filter="filter"/>

  </div>
</template>

<script>
  import filterArea from "./Filter.vue";
  export default {
    components: {
      filterArea
    },
    props: ['filter']
  };
</script>