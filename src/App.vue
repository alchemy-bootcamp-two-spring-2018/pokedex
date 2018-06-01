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
      nameSort: 1,
      typeSort: 1,
      atkSort: 1,
      defSort: 1,
      filterType: '',
      sortType: '',
      minatk: 0,
      mindef: 0
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
      // Make sure sorting options persist through type changes
      switch(this.sortType) {
        case'name':
          this.nameSort = -this.nameSort;
          this.sortName();
          break;
        case'type':
          this.typeSort = -this.typeSort;
          this.sortType(-this.typeSort);
          break;
        case'atk':
          this.atkSort = -this.atkSort;
          this.sortAtk(-this.atkSort);
          break;
        case'def':
          this.defSort = -this.defSort;
          this.sortDef(-this.defSort);
          break;
      }
      switch(this.filterType) {
        case('atk'):
          this.filterAtk(this.minatk);
          break;
        case('def'):
          this.filterDef(this.mindef);
          break;
      }
    },
    displayAll() {
      this.filteredList = this.pokeList;
    },
    sortName() {
      this.sortType = 'name';
      // Using nameSort helps toggle the order (a-z || z-a)
      if(this.nameSort !== 1) {
        // Compare strings
        this.filteredList.sort((a, b) => ('' + b.pokemon).localeCompare(a.pokemon));
      } else {
        // Compare strings
        this.filteredList.sort((a, b) => ('' + a.pokemon).localeCompare(b.pokemon));
      }
        this.nameSort = -this.nameSort;
    },
    sortType() {
      this.sortType = 'type';
      // Using typeSort helps toggle the order (a-z || z-a)
      if(this.typeSort !== 1) {
        // Compare strings
        this.filteredList.sort((a, b) => ('' + b.pokemon).localeCompare(a.pokemon));
      } else {
        // Compare strings
        this.filteredList.sort((a, b) => ('' + a.pokemon).localeCompare(b.pokemon));
      }
        this.typeSort = -this.typeSort;
    },
    sortAtk() {
      this.sortType = 'atk';
      // Using atkSort helps toggle the order (a-z || z-a)
      if(this.atkSort !== 1) {
        this.filteredList.sort((a, b) => b.attack - a.attack);
      } else {
        this.filteredList.sort((a, b) => a.attack - b.attack);
      }
        this.atkSort = -this.atkSort;
    },
    sortDef() {
      this.sortType = 'def';
      // Using defSort helps toggle the order (a-z || z-a)
      if(this.defSort !== 1) {
        this.filteredList.sort((a, b) => b.defense - a.defense);
        } else {
          this.filteredList.sort((a, b) => a.defense - b.defense);
        }
          this.defSort = -this.defSort;
    },
    filterAtk(minAtk) {
      this.filterType = 'atk';
      // masterList used to store current list to revert back to
      if(this.masterList != this.filteredList) {
        this.filteredList = this.masterList;
      }
      this.filteredList = this.filteredList.filter(a => a.attack >= minAtk);
    },
    filterDef(minDef) {
      this.filterType = 'def';
      // masterList used to store current list to revert back to
      if(this.masterList != this.filteredList) {
        this.filteredList = this.masterList;
      }
      this.filteredList = this.filteredList.filter(a => a.defense >= minDef);
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
