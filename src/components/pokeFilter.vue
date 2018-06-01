<template>
  <div class="pokeTile">
      <span>Filter by Type</span>
      <input v-model="filter.type">
  </div>
</template>

<script>
import pokeDex from '../pokemon.js'
export default {

  data() {
    return {
      list: pokeDex
    }
  },

  props: ['filter'],

  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
