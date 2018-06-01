<template>
  <div>
    <select v-model="filter.type" class="pokemon-type">
      <option value="all">Select Type</option>
      <option value="water">Water</option>
      <option value="electric">Electric</option>
      <option value="ice">Ice</option>
    </select>
      <input v-model="filter.pokemon">
  </div>
</template>
<script>
  export default {

    props: ['filter']
  }

</script>