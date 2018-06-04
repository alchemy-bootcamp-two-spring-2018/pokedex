<template>
  <div>
    <section class="tile-display">
      <Tile
        :tiles="list"
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
  props: {
    list: Array,
  }
};
</script>

<style>
</style>