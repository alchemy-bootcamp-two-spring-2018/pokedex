<template>
  <div>
    <tile 
    v-bind:pokeTiles= "list"
    />
  </div>
</template>

<script>
import tile from './tile.vue'

export default {

    props: {
      list: Array,
    } ,

    components: {
        tile,
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
