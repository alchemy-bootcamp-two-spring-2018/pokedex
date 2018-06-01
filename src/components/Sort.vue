<template>
  <div>
    <h1>This is a sort option</h1>

    <select v-model="sort.by">
      <option disabled value="">Sort</option>
      <option>Name</option>
      <option>Type</option>
      <option>HP</option>
    </select>
  </div>
</template>

<script>

export default {

  props: ['sort']
};

</script>

<style>

</style>