<template>
  <div>
    <img
      v-if="selectedPokemon"
     :src="selectedPokemon.url_image"
    >
    <div class="pokemon-detail" v-if="selectedPokemon">
      <p>Pokemon: {{selectedPokemon.pokemon}}</p>
      <p>Type: {{selectedPokemon.type_1}}, {{selectedPokemon.type_2}}</p>
      <p>ID: {{selectedPokemon.id}}</p>
      <p>HP: {{selectedPokemon.hp}}</p>
      <p>Attack: {{selectedPokemon.attack}}</p>
      <p>Defense: {{selectedPokemon.defense}}</p>
      <p>Speed: {{selectedPokemon.speed}}</p>
      <p>Ability: {{selectedPokemon.ability_1}}</p>
    </div>
  </div>
</template>
<script>
  export default {
    props: ['selectedPokemon']
  };
</script>
<style>
h1{
  color: blue;
}
img {
  width: 250px;
  height: 250px;
}
.pokemon-detail {
  font-family: 'arcade';
  margin-top: 150px;
  color: rgba(216, 216, 216, 0.767);
}
@font-face {
  font-family: 'arcade';
  src: url(../assets/bold_dot_digital-7.ttf) format('truetype');
}
</style>