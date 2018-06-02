<template>
  <span>
    <h3>This is our Pokedex SORT component!</h3>
    <select v-model="sort.prop">
      <option value="pokemon">Name</option>
      <option value="type_1">Type 1</option>
      <option value="attack">Attack</option>
      <option value="defense">Defense</option>
    </select>
  </span>
</template>

<script>

export default {

  props: ['sort']

};

</script>


<style>

</style>