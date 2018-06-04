<template>
  <span>
    Sort pokemon by:
    <select v-model="sort.prop">
      <option value="id">Pokemon id#</option>
      <option value="pokemon">Name</option>
      <option value="type_1">Type 1</option>
      <option value="attack">Attack</option>
      <option value="defense">Defense</option>
    </select>
    <select v-model="order.prop">
      <option value="ascending">Low to high</option>
      <option value="descending">High to low</option>
    </select>
  </span>
</template>

<script>

export default {

  props: ['sort', 'order']

};

</script>


<style>

</style>