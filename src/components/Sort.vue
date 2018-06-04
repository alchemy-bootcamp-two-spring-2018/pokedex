<template>
  <div>
    <select v-model="sort.by">
      <option disabled value="">Sort</option>
      <option value="">None</option>
      <option value="pokemon">Name</option>
      <option value="type_1">Type</option>
      <option value="hp">HP</option>
      <option value="defense">Defense</option>
    </select>
  </div>
</template>

<script>

export default {

  props: ['sort']

};

</script>

<style>

select {
  font-size: 1.25em;
}

</style>