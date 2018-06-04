<template>
  <div>
      <p>Sort by name or id</p>
      <input
      v-model="sorted.sortValue"
      >
      <button
      v.model="sorted.sort"
      >ID#</button>
      <!-- <input 
      v-model="filter.type"
      @change="$emit('change')"
      > -->
  </div>
</template>

<script>

export default {
//props is data that is passed down from a parent to the component
  props: ['sorted'],

  }

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
