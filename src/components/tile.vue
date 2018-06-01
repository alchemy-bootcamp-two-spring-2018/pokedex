<template>
  <div class="pokeTile">
    <div
    v-for = 'pokeDex in pokeTiles'
    v-bind:key = 'pokeDex.id'
    class="containerTile"> 
      <span>{{pokeDex.pokemon}}</span>
      <span>{{pokeDex.type_1}}</span>
      <img v-bind:src="pokeDex.url_image">
    </div>
  </div>
</template>

<script>

export default {
  props: {
    pokeTiles: Array,
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

#containerTile {
  display: flex;
  width: 100px;
  background-color: gray;
}
span {
  display: block;
}

img {
  width: 75px;
}
</style>
