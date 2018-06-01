<template>
  <div class="header">
    <PokeFilter :filtered="filtered" :types="types"/>
    <PokeSort :sorted="sorted"/>

  </div>
</template>

<script>
import PokeFilter from './PokeFilter'
import PokeSort from './PokeSort'

export default {
  components: {
    PokeFilter,
    PokeSort
  },
  props: ['filtered', 'types', 'sorted'],
  methods: {
    updateFiltered(type) {
      this.filtered.type = type;
    }
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  display: flex;
}
</style>
