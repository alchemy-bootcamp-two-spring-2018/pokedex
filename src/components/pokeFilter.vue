<template>
  <div class="pokeTile">
      <span>Filter by Type</span>
      <input 
      v-model="filter.type"
      @change="$emit('change')"
      >
  </div>
</template>

<script>

export default {

  props: ['filter'],

  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
