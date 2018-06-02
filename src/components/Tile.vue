<template>
  <span class="tile">
      <h2 v-bind:style="{ 'color': pokemon.color_1 }">{{pokemon.pokemon}}</h2>
      <img v-bind:src="pokemon.url_image">
        <p>Type 1: {{pokemon.type_1}}</p>
        <p>Type 2: {{pokemon.type_2}}</p>
        <p>HP: {{pokemon.hp}}</p>
        <p>Attack: {{pokemon.attack}}</p>
        <p>Speed: {{pokemon.speed}}</p>
        <p>Defense: {{pokemon.defense}}</p>
        <p>Special Attack: {{pokemon.special_defense}}</p>
        <p>Special Defense: {{pokemon.special_defense}}</p>
  </span>
</template>

<script>

export default {
  props: ['pokemon']
};

</script>


<style scoped>

h2 {
  font-size: 16px;
  margin: 0px;
}
.tile {
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  width: 178px;
  height: fit-content;
  border: 3px solid black;
  text-transform: capitalize;
  padding: 15px;
  margin: 5px;
  border-radius: 20px;
  background-color: rgb(255, 255, 245);
}

.tile:hover {
  background-color: rgb(255, 255, 219);
}

p {
  margin: 0px;
}
img {
  width: 80px;
}

</style>