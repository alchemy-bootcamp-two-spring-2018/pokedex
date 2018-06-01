<template>
  <div class="sort">
    <h2>Sort</h2>
    <button @click="sortByAttack">attack</button>
    <button @click="sortByName">name</button>
  </div>
</template>

<script>
export default {
  props: ['sorted'],
  methods: {
    sortByAttack() {
      this.sorted.sortBy='attack'
    },
     sortByName() {
      this.sorted.sortBy='name'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
