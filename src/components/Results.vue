<template>
  <section>
    <div class="results">
      <Tile 
        v-for="pokemon in pokeList"
        :key="pokemon.id"
        :pokemon="pokemon"
        v-on:selected="selected = pokemon"
        />
        
      <Viewer :selectedPokemon="selected"/>
    </div>
  </section>
</template>

<script>
import Tile from './Tile'
import Viewer from './Viewer'


export default {
  data() {
    return {
      selected: null
    }
  },
  components: {
    Tile,
    Viewer
  },
  methods: {
    updateSelected(pokemon) {
      this.selected = pokemon;
      console.log(pokemon);
    }
  },
  props: ['pokeList']

}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.results {
  display: flex;
  flex-wrap: wrap;
  transition: all 1s ease;

}
</style>
