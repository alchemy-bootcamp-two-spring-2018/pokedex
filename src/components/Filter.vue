<template>
  <div>
    <h3>Select Type</h3>
    <select v-model="filter.type" class="pokemon-type">
      <option value="all">All</option>
      <option value="water">Water</option>
      <option value="electric">Electric</option>
      <option value="ice">Ice</option>
      <option value="fire">fire</option>
      <option value="ground">ground</option>
      <option value="psychic">psychic</option>
      <option value="dragon">dragon</option>
      <option value="dark">dark</option>
      <option value="fairy">fairy</option>
      <option value="ghost">ghost</option>
      <option value="poison">poison</option>
      <option value="rock">rock</option>
      <option value="bug">bug</option>
      <option value="steel">steel</option>
      <option value="flying">flying</option>
      <option value="grass">grass</option>
    </select>
    <h3>Minimum Defense</h3>
      <input v-model="filter.defense" type="numbers">
  </div>
</template>
<script>
  export default {

    props: ['filter']
  }

</script>
<style scoped>
  div {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
  }
  h3 {
    margin-left: 10px;
    margin-right: 10px;
  }
</style>