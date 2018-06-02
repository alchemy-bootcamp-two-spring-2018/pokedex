<template>
  <span>
      <span class="cards">
        <Tile
        v-for="pokemon in finalSort"
        v-bind:key="pokemon.id"
        :pokemon="pokemon"
        />
      </span>
  </span>
</template>

<script>
import Tile from './Tile.vue';

export default {

  props: ['finalSort'],

  components: {
    Tile
  }
};

</script>


<style>
.cards {
  display: flex;
  flex-flow: row wrap;
}
</style>