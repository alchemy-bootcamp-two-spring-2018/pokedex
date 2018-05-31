<template>
  <div class="pokeTile">
    <div
    v-for = 'pokeDex in list'
    v-bind:key = 'pokeDex.id'
    > 
      <span>{{pokeDex.pokemon}}</span>
      <img v-bind:src="pokeDex.url_image">
    </div>
  </div>
</template>

<script>
import pokeDex from '../pokemon.js'
export default {
  data() {
    return {
      list: pokeDex
    }
  },
  props: {
    name: String,
    type: String,
    img: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
