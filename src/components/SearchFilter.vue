<template>
  <div class="filter-box">
    <h2>Filter</h2>
      <select name="" id="" v-model="filter.type">
        <option value="grass">Grass</option>
        <option value="fire">Fire</option>
        <option value="electric">Electric</option>
      </select>

      <label>Min. Atk: </label>
      <input v-model="filter.attack" type="number" min="0">
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
