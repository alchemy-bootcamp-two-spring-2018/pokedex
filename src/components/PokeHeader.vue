<template>
  <div class="header">
    <PokeFilter :filtered="filtered"/>
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
  props: ['filtered', 'sorted'],
  methods: {
    updateFiltered(type) {
      this.filtered.type = type;
    }
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
