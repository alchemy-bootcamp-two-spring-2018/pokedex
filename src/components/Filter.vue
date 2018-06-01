<template>
  <div>
    <h1>This is a Filter</h1>
   
    <select v-model="filterSelection.type">
      <option disabled value="">Select type</option>
      <option>grass</option>
      <option>fire</option>
      <option>water</option>
      <option>bug</option>
    </select>

    <input v-model="filterSelection.hp" placeholder="Enter a minimum HP">
    <!-- <span>Select Type: {{ filterSelection.type }}</span> -->
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