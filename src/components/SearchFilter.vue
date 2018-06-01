<template>
  <div class="filter-box">
    <h2>Filter</h2>
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
