<template>
  <div>
    <h1>This is a Filter</h1>

    <select v-model="filterSelection.type">
      <option disabled value="">Select type</option>
      <option value="all">All</option>
      <option>Bug</option>
      <option>Dark</option>
      <option>Dragon</option>
      <option>Electric</option>
      <option>Fairy</option>
      <option>Fighting</option>
      <option>Fire</option>
      <option>Ghost</option>
      <option>Grass</option>
      <option>Ground</option>
      <option>Ice</option>
      <option>Normal</option>
      <option>Poison</option>
      <option>Psychic</option>
      <option>Rock</option>
      <option>Steel</option>
      <option>Water</option>
    </select>

    <input v-model="filterSelection.hp" placeholder="Enter a minimum HP">
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