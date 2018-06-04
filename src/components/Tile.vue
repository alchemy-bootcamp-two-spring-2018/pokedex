<template>
  <div class = "container" >
    <div class = "tile" v-bind:style="{ background: pokemon.color_1 }">
      <img :src="pokemon.url_image">
      <p class = "name"> {{ pokemon.pokemon }} </p>
      <p> HP: {{pokemon.hp}} </p>
      <p> Defense: {{pokemon.defense}} </p>
      <p> Type: {{pokemon.type_1}} </p>
    </div>
  </div>
</template>

<script>

export default {

  props: ['pokemon']

};

</script>

<style>

p {
color: white;
font-size: 16px;
font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
text-transform: capitalize;

}
.name {
  text-transform: uppercase;
  font-size: 18px;
}

img {
  width: 150px;
  background-color: white;
  border: 1px solid black;

}
.tile {
  text-align: center;
  display: inline-block;
  weight: 300 px;
  border: 10px solid yellow;
  border-radius: 15px;
  margin: 10px;
  padding: 10px;
  
}
.container {
min-width: 250px;
display: inline;

}
</style>
