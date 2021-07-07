<template>
  <div class="pokeTile">
      <span>Filter by Type</span>
      <select
      v-model="filter.type"
      >
        <option
        v-for = 'types in typeList'
        v-bind:key = 'types.name'
        >{{types.name}}</option>
      </select>

  </div>
</template>

<script>
import typeList from '../dropdownData.js'

export default {
  data() {
    return {
      typeList: typeList
    }
  },
//props is data that is passed down from a parent to the component
  props: ['filter'],

  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
