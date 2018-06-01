<template>
  <div class="filter-box">
    <h2>Filter By Element</h2>
    <p>Please Enter an Element</p>
    <p>EX: Water, Fire, Earth</p>
      <input v-model="filter.type">
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
