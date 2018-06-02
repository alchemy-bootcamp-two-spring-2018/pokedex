<template>
  <div>
      <p>Sort by name or id</p>
      <select
      v-model="sorted.sortValue"
      >
        <option
        v-for = 'types in sortOptions'
        v-bind:key = 'types.name'
        >{{types.value}}</option>
      </select>
      
      <!-- <input 
      v-model="filter.type"
      @change="$emit('change')"
      > -->
  </div>
</template>

<script>
import sortOptions from '../sortDropdown.js'

export default {
  data() {
    return {
      sortOptions: sortOptions
    }
  },
//props is data that is passed down from a parent to the component
  props: ['sorted'],

  }

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
