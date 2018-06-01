<template>
    <div>
      <pokeFilter
      v-bind:filter="filter"
      />
      <Sorting
      v-bind:sorted="filter"
      v-bind:nameSort="nameSort"
      />
      
    </div>
</template>

<script>
import pokeFilter from './pokeFilter.vue'
import Sorting from './Sort.vue'

export default {

    props: {
        filter: Object,
        nameSort: Function,
    },

    components: {
        pokeFilter,
        Sorting,
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

div{
      display: inline-block;
      margin: 10px;
}

</style>