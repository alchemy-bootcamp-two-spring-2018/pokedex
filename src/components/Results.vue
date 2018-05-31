<template>
  <div>
    <ul>
      <li
        class="listItems"
        v-for="pokemon in list"
        :key="pokemon.id"
      >
        <div class="card">
          <img :src="pokemon.url_image" alt="Pokemon image" style="width:75px">
          <div class="container">
            <h4><b>{{pokemon.pokemon.toUpperCase()}}</b></h4>
            <p>Type: {{pokemon.type_1.toUpperCase()}}</p>
            <p>HP: {{pokemon.hp}}</p>
            <p>Attack: {{pokemon.attack}}</p>
            <p>Defense: {{pokemon.defense}}</p>
          </div>
        </div>

      </li>
    </ul>
  </div>
</template>

<script>
import pokemon from '../../pokemon.js';

export default {
  data() {
    return {
      list: pokemon
    }
  }
}
</script>

<style>
ul {
  list-style-type: none;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 0;
}

p {
  line-height: 2px;
}

/* card styling grabbed from https://www.w3schools.com/howto/howto_css_cards.asp */
.card {
/* Add shadows to create the "card" effect */
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  margin: 10px;
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

/* Add some padding inside the card container */
.container {
  padding: 2px 16px;
}

</style>
