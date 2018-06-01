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
      />
        <!-- @def="sortDef"
        @minatk="filterAtk($event)"
        @mindef="filterDef($event)" -->
      <div id="atk-def">
        Min-Atk:
        <input
            type="number"
            v-model.number="minatk"
            @change="filterAtk(minatk)"
        />
        Min-Def: 
        <input
            type="number"
            v-model.number="mindef"
            @change="filterDef(mindef)"
        />
      </div>
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
      filteredList: {},
      masterList: {},
      atkSort: false,
      defSort: false,
      nameSort: false,
      typeSort: false,
      minatk: '',
      mindef: ''
    }
  },
  components: {
    PokeHeader,
    PokeResults
  },
  methods: {
    filterTypes(pokeType) {
      this.filteredList = pokeList.filter(a => a.type_1 === pokeType);
      // tempList used to revert back from any array mutations
      this.masterList = this.filteredList;
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
      // masterList used to store current list to revert back to
      if(this.masterList != this.filteredList) {
        this.filteredList = this.masterList;
      }
      this.filteredList = this.filteredList.filter(a => a.attack > minAtk);
    },
    filterDef(minDef) {
      console.log('defense method', minDef);
      // masterList used to store current list to revert back to
      if(this.masterList != this.filteredList) {
        this.filteredList = this.masterList;
      }
      this.filteredList = this.filteredList.filter(a => a.defense > minDef);
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
