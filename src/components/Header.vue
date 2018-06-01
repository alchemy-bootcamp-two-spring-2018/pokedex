<template>
    <div>
      <pokeFilter
      v-bind:filter="filter"
      @change="updatePokedex"
      />
    
    </div>
</template>

<script>
import pokeFilter from './pokeFilter.vue'

export default {

    props: {
        filter: String,
    },

    components: {
        pokeFilter,
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>