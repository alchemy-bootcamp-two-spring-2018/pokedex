<template>
  <div class="filter-box">
    <h2>Filter</h2>
      <label>Type: </label>
      <input v-model="filter.type">
      <label>Min. Atk: </label>
      <input v-model="filter.attack">
  </div>
</template>

<script>
export default {
  props: ['filter'],
};
</script>

<style>
.filter-box {
  float: right;
}
</style>
