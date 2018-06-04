<template>
  <div class="filter-box">
    <h2>Filter</h2>
      <label>Type: </label>
      <select v-model="filter.type">
        <option disabled value="">Please select a type</option>
        <!-- <option value=""></option> -->
        <option value="grass">Grass</option>
        <option value="fire">Fire</option>
        <option value="psychic">Psychic</option>
        <option value="fighting">Fighting</option>
        <option value="dark">Dark</option>
        <option value="flying">Flying</option>
        <option value="ground">Ground</option>
        <option value="bug">Bug</option>
        <option value="ice">Ice</option>
        <option value="water">Water</option>
        <option value="electric">Electric</option>
        <option value="poison">Poison</option>
        <option value="fairy">Fairy</option>
        <option value="rock">Rock</option>
        <option value="ghost">Ghost</option>
        <option value="dragon">Dragon</option>
        <option value="steel">Steel</option>
        <option value="normal">Normal</option>
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
