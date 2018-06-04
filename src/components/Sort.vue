<template>
  <div class="sortbox">
    <h2>Sort</h2>
    <select v-model="chosenSort.prop">
      <option disabled value="">Sort by: </option>
      <option value="pokemon">name</option>
      <option value="attack">attack</option>
      <option value="hp">HP</option>
      <option value="defense">defense</option>
    </select>
  </div>
</template>

<script>
export default {
  props: ['chosenSort']
};
</script>

<style>
.sortbox {
  float: left;
}

</style>
