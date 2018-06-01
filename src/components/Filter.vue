<template>
  <div>
    <h1>This is a Filter</h1>
    <input v-model="filterSelection.type">
  </div>
</template>

<script>




export default {
  props: [
    'filterSelection'
  ]
};

</script>

<style>

</style>