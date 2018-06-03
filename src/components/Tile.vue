<template>
  <span class="tile" :style="{ 'background-color': pokemon.color_1 }">
      <span class="inside">
        <h2 :style="{ 'color': pokemon.color_1 }">{{pokemon.pokemon}}</h2>
        <span class="imgFrame" :style="{ 'border-color': pokemon.color_1 }"><img :src="pokemon.url_image"></span>
        <p>Type 1: {{pokemon.type_1}}</p>
        <p>Type 2: {{pokemon.type_2}}</p>
        <p>HP: {{pokemon.hp}}</p>
        <p>Attack: {{pokemon.attack}}</p>
        <p>Speed: {{pokemon.speed}}</p>
        <p>Defense: {{pokemon.defense}}</p>
        <p>Special Attack: {{pokemon.special_defense}}</p>
        <p>Special Defense: {{pokemon.special_defense}}</p>
      </span>
  </span>
</template>

<script>

export default {
  props: ['pokemon']
};

</script>


<style scoped>

h2 {
  color: yellow;
  text-shadow: -2px 0 rgba(0, 0, 0, 0.6), 0 2px rgba(0, 0, 0, 0.6), 2px 0 rgba(0, 0, 0, 0.6), 0 -2px rgba(0, 0, 0, 0.6);
  font-size: 16px;
  margin: 0px;
  margin-bottom: 5px;
}
.tile {
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  width: 200px;
  height: 310px;
  border: 3px solid black;
  text-transform: capitalize;
  margin: 5px;
  border-radius: 15px;
  transition: 0.3s;
}

.tile:hover {
  transform: scale(1.25);
  box-shadow: -10px 10px rgba(0, 0, 0, 0.514), 0 0 black;
}
.inside {
  color: rgb(255, 255, 255);
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  width: 166px;
  height: 335px;
  border: 2px solid rgba(0, 0, 0, 0.438);
  text-transform: capitalize;
  padding: 10px;
  margin: 5px;
  border-radius: 10px;
  background-color: rgba(0, 0, 0, 0.5);
}

.imgFrame {
  margin-bottom: 5px;
  background-color: white;
  border: 3px solid;
  border-radius: 5px;
  padding: 3px;
}

p {
  margin: 0px;
}
img {
  width: 80px;
}

</style>