<template>
  <div class="sortbox">
    <h2>Sort</h2>
    <select v-model="chosenSort.prop">
      <option value="name">name</option>
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
