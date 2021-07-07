<template>
  <div class="pokeTile">
    <div
    v-for = 'pokeDex in pokeTiles'
    v-bind:key = 'pokeDex.id'
    v-bind:style="{ backgroundColor: pokeDex.color_1 }" 
    class="containerTile"> 
      <span>{{pokeDex.pokemon}}</span>
      <span>{{pokeDex.type_1}}</span>
      <img v-bind:src="pokeDex.url_image">
      <div>
        <span>HP: {{pokeDex.hp}}</span>
        <span>Attack: {{pokeDex.attack}}</span>
        <span>Defense: {{pokeDex.defense}}</span>
        <span>Sp.Attack: {{pokeDex.special_attack}}</span>
        <span>Sp.Defense: {{pokeDex.special_defense}}</span>
        <span>Speed: {{pokeDex.speed}}</span>
      </div>
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

.containerTile {
  display: inline-block;
  background-color: rgb(245, 245, 245);
  margin: 5px;
  border-radius: 7.5px;
  width: 300px;
  opacity: 0.75;
}

.containerTile:hover{
  opacity: 1;
}

span {
  display: block;
}

img {
  width: 200px;
}
</style>
