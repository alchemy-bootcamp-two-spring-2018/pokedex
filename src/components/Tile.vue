<template>
  <span>
    <section class="cards" v-if="pokemonProp">
      <ul>
      <li
      class="tile"
      v-for="pokemon in pokemonProp"
      v-bind:key="pokemon.id"
      >
          <h2>{{pokemon.pokemon}}</h2>
          <img v-bind:src="pokemon.url_image">
            <p>Type 1: {{pokemon.type_1}}</p>
            <p>Attack: {{pokemon.attack}}</p>
            <p>Defense: {{pokemon.defense}}</p>
      </li>
      </ul>
    </section>
    <p v-else>Select a pokemon to learn more!</p>
  </span>
</template>

<script>

export default {
  props: ['pokemonProp']
};

</script>


<style scoped>

h2 {
  margin: 0px;
}

.tile {
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  width: 162px;
  height: fit-content;
  border: 2px solid black;
  text-transform: capitalize;
  padding: 15px;
  margin: 5px;
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