<template>
  <div class="sort">
    <h2>Sort</h2>
    <button @click="sortByID">ID</button>
    <button @click="sortByName">Name</button>
  </div>
</template>

<script>
export default {
  props: ['sorted'],
  methods: {
    sortByID() {
      this.sorted.sortBy = 'id'
    },
     sortByName() {
      this.sorted.sortBy = 'name'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
