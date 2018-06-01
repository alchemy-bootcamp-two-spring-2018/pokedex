<template>
  <div id="app">
    <h1>Manipulate your poke search!</h1>
    <button @click="displayAll">-o-</button>
    <div id="app-main">
      <poke-header id="header"
        :pokeList="remDupes"
        @change="filterTypes"
        @name="sortName"
        @type="sortType"
        @atk="sortAtk"
        @def="sortDef"
        @minatk="filterAtk"
        @mindef="filterDef"
      />
      <poke-results id="results"
        :banana="filteredList"
      />
    </div>
  </div>
</template>

<script>
import PokeHeader from './components/PokeHeader.vue'
import PokeResults from './components/PokeResults.vue'
import pokeList from './assets/pokemon.js'

export default {
  name: 'app',
  data() {
    return {
      pokeList: pokeList,
      filteredList: '',
      atkSort: false,
      defSort: false,
      nameSort: false,
      typeSort: false
    }
  },
  components: {
    PokeHeader,
    PokeResults
  },
  methods: {
    filterTypes(pokeType) {
      this.filteredList = pokeList.filter(a => a.type_1 === pokeType);
    },
    displayAll() {
      this.filteredList = this.pokeList;
    },
    sortName() {
      // Using nameSort helps toggle the order (a-z || z-a)
      if(this.nameSort) {
        this.nameSort = false;
      // Compare strings
        this.filteredList.sort((a, b) => ('' + b.pokemon).localeCompare(a.pokemon));
      } else {
        this.nameSort = true;
      // Compare strings
        this.filteredList.sort((a, b) => ('' + a.pokemon).localeCompare(b.pokemon));
      }
    },
    sortType() {
      // Using typeSort helps toggle the order (a-z || z-a)
      if(this.typeSort) {
        this.typeSort = false;
      // Compare strings
        this.filteredList.sort((a, b) => ('' + b.pokemon).localeCompare(a.pokemon));
      } else {
        this.typeSort = true;
      // Compare strings
        this.filteredList.sort((a, b) => ('' + a.pokemon).localeCompare(b.pokemon));
      }
    },
    sortAtk() {
      // Using atkSort helps toggle the order (a-z || z-a)
      if(this.atkSort) {
        this.atkSort = false;
        this.filteredList.sort((a, b) => b.attack - a.attack);
      } else {
        this.atkSort = true;
        this.filteredList.sort((a, b) => a.attack - b.attack);
      }
    },
    sortDef() {
      // Using defSort helps toggle the order (a-z || z-a)
      if(this.defSort) {
        this.defSort = false;
        this.filteredList.sort((a, b) => b.defense - a.defense);
        } else {
          this.defSort = true;
          this.filteredList.sort((a, b) => a.defense - b.defense);
        }
    },
    filterAtk(minAtk) {
      console.log('attack method');
      this.filteredList.filter(a => a.attak > minAtk);
    },
    filterDef(minDef) {
      console.log('defense method');
      this.filteredList.filter(a => a.attak > minDef);
    }
  },
  computed: {
    remDupes() {
      return this.pokeList.filter((obj, pos, arr) => {
          return this.pokeList.map(mapObj => mapObj.type_1).indexOf(obj.type_1) === pos;
      });
    }
  }
}
</script>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
}
#app-main {
  display: flex;
  flex-direction: column;
  margin: auto;
  text-align: center;
  width: 600px;
}

h1 {
  text-align: center;
}

button {
  align-self: center;
  font-size: 3rem;
  cursor: pointer;
  background: radial-gradient(red, white);
  color: black;
  border-radius: 100%;
  width: fit-content;
}


</style>
