<template>
  <div class="sortbox">
    <h2>Sort By Attributes</h2>
    <select>
      <option value="id">ID</option>
      <option value="hp">HP</option>
      <option value="attack">Attack</option>
      <option value="defense">Defense</option>
    </select>
  </div>
</template>

<script>
export default {
  props: ['sort'],
};
</script>

<style>
.sortbox {
  float: left;
}

</style>
