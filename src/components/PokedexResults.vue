<template>
  <section v-if="order.prop === 'descending'">
    <span>
      <span class="cards">
        <Tile
        v-for="pokemon in sortDescending"
        v-bind:key="pokemon.id"
        :pokemon="pokemon"
        />
      </span>
    </span>
  </section>
  <section v-else>
     <span>
      <span class="cards">
        <Tile
        v-for="pokemon in sortAscending"
        v-bind:key="pokemon.id"
        :pokemon="pokemon"
        />
      </span>
    </span>
  </section>
</template>

<script>
import Tile from './Tile.vue';

export default {

  props: ['sortAscending', 'sortDescending', 'order'],

  components: {
    Tile
  }
};

</script>


<style>
.cards {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
}
</style>