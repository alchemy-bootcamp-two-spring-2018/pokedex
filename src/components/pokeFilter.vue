<template>
  <div class="pokeTile">
      <span>Filter by Type</span>
      <input 
      v-model="filter.type"
      >
  </div>
</template>

<script>

export default {
//props is data that is passed down from a parent to the component
  props: ['filter'],

  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
