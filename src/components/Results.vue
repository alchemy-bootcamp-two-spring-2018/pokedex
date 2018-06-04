<template>
  <div>
    <section class="tile-display">
      <Tile
        v-for="pokemon in sortedList"
        :key="pokemon.id"
        :tiles="pokemon"
      />
    </section>
  </div>
  
</template>

<script>
import Tile from './Tile.vue';

export default {
  components: {
    Tile
  },

  props: ['sortedList']
};
</script>

<style>
.tile-display {
  list-style-type: none;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  padding: 0;
}
</style>