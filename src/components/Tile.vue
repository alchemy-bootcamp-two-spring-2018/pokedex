<template>
  <span>
    <section class="cards" v-if="pokemonProp">
      <span
      class="tile"
      v-for="pokemon in sortedByType"
      v-bind:key="pokemon.id"
      >
          <h2 v-bind:style="{ 'color': pokemon.color_1 }">{{pokemon.pokemon}}</h2>
          <img v-bind:src="pokemon.url_image">
            <p>Type 1: {{pokemon.type_1}}</p>
            <p>Type 2: {{pokemon.type_2}}</p>
            <p>Attack: {{pokemon.attack}}</p>
            <p>Defense: {{pokemon.defense}}</p>
      </span>
    </section>
    <p v-else>Select a pokemon to learn more!</p>
  </span>
</template>

<script>

export default {
  props: ['pokemonProp', 'getFiltered', 'sortedByName', 'sortedByType']
};

</script>


<style scoped>

h2 {
  font-size: 18px;
  margin: 0px;
}

.cards {
  display: flex;
  flex-flow: row wrap;
}

.tile {
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  width: 174px;
  height: fit-content;
  border: 2px solid black;
  background-color: rgb(249, 244, 244);
  text-transform: capitalize;
  padding: 15px;
  margin: 5px;
  border-radius: 20px;
}

.tile p {
  margin: 0px;
}

.tile img {
  width: 80px;
}

ul {
  width: fit-content;
  text-align: center;
  list-style-type: none;
}

</style>