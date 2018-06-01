<template>
  <div id="app">
    <h1>Poke Dex</h1>
    <section id="header-filter">
      <Header
        v-bind:filter="chosenFilter"
        
      />
    </section>
    <section id="pokemon-display">
      <Results v-bind:list= "pocketMonsters"
      />
    </section>
  </div>
</template>

<script>
import pokeDex from './pokemon.js'
import Results from './components/Results.vue'
import Header from './components/Header.vue'

export default {
  name: 'app',
  data(){
    return {
      list: pokeDex,
      chosenFilter: {
        type: '',
      }
    }
  },
  components: {
    Results,
    Header
  },

  computed: {
    pocketMonsters() {
      let filteredPokemon = [];
      console.log(this.chosenFilter.type)
      for (let i in this.list) {
        if(this.list[i].type_1 === this.chosenFilter.type) {
          filteredPokemon.push(this.list[i])
        }
      }
      console.log(filteredPokemon)
      return filteredPokemon
    }
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
