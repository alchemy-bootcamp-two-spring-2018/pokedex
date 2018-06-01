<template>
  <section class="content">
    <div class="results">
      <Tile 
        v-for="pokemon in pokeList"
        :key="pokemon.id"
        :pokemon="pokemon"
        v-on:selected="selected = pokemon"
        />
    </div>
    <Viewer :selectedPokemon="selected"/>
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
.content {
  display: grid;
  grid-template: auto / 1fr 1fr;
}

.results {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  transition: all 1s ease;
  border: 1px solid black;
  border-radius: 25px;
  background: white;
  margin: 30px;
  overflow: scroll;
  height: 600px;
}

</style>
