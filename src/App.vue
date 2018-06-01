<template>
  <div id="app">
    <h1>Poke Dex</h1>
    <section id="header-filter">
      <Header
        v-bind:filter="chosenFilter"
        v-bind:nameSort="sortByName"
      />
    </section>
    <section id="pokemon-display">
      <Results v-bind:list="pocketMonsters"
      />
      <p>Get started by typing in your favorite Pokemon type (Water, Fire, Electric, Ground, etc).</p>
    </section>
  </div>
</template>

<script>
import pokeDex from './pokemon.js'
import Results from './components/Results.vue'
import Header from './components/Header.vue'

export default {
  name: 'app',
  //data is a data initialization function that happens at the BEGINNING of a components life
  data(){
    return {
      list: pokeDex,
      chosenFilter: {
        type: '',
        sort: ''
      }
    }
  },
  components: {
    Results,
    Header
  },
//these are functions but when they are used they don't need to double parens at the end, because they
//are PROPERTIES, so they are automatically working, they can have their information passed down to
//lower components
  computed: {
    //refactor this to use the filter array method
    pocketMonsters() {
      return this.list.filter(pokemon => {
        return (this.chosenFilter.type === '' || pokemon.type_1 === this.chosenFilter.type)
      })
    }
  },

  methods: {
    sortByName() {
      console.log('sortingIsWorking', this.pocketMonsters)
      this.pocketMonsters.sort();
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

#header-filter {
  display: inline-block;
}

p {
  color:#25394d91;
  font-size: .8em;
}

</style>
