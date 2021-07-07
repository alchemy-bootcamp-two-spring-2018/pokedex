<template>
    <div>
      <pokeFilter
      v-bind:filter="filter"
      />
      <Sorting
      v-bind:sorted="filter"
      />
      
    </div>
</template>

<script>
import pokeFilter from './pokeFilter.vue'
import Sorting from './Sort.vue'

export default {

    props: {
        filter: Object,
    },

    components: {
        pokeFilter,
        Sorting,
    }
  }

</script>

<style scoped>

div{
      display: inline-block;
      margin: 10px;
}

</style>