<template>
  <div id="app">
    <h1>Manipulate your poke search!</h1>
    <img src="./assets/ball.png" @click="displayAll">
    <div id="app-main">
      <poke-header id="header"
        :pokeList="remDupes"
        @change="filterTypes"
        @name="sortName"
        @type="sortType"
        @atk="sortAtk"
      />
      <div id="atk-def">
        <label>
        Min-Atk:
        <input
            type="number"
            v-model.number="minatk"
            @change="filterAtk(minatk)"
        /></label>
        <label>
        Min-Def: 
        <input
            type="number"
            v-model.number="mindef"
            @change="filterDef(mindef)"
        /></label>
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
      filterStyle: '',
      sortStyle: '',
      minatk: 0,
      mindef: 0
    }
  },

  // COMPONENTS
  components: {
    PokeHeader,
    PokeResults
  },

  // METHODS
  methods: {
    filterTypes(pokeType) {
      this.filteredList = pokeList.filter(a => a.type_1 === pokeType);
      // tempList used to revert back from any array mutations
      this.masterList = this.filteredList;
      // Make sure sorting options persist through type changes
      switch(this.sortStyle) {
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
      switch(this.filterStyle) {
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
      this.sortStyle = 'name';
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
      this.sortStyle = 'type';
      // Using typeSort helps toggle the order (a-z || z-a)
      if(this.typeSort !== 1) {
        // Compare strings
        this.filteredList.sort((a, b) => ('' + b.type_1).localeCompare(a.type_1));
      } else {
        // Compare strings
        this.filteredList.sort((a, b) => ('' + a.type_1).localeCompare(b.type_1));
      }
        this.typeSort = -this.typeSort;
    },

    sortAtk() {
      this.sortStyle = 'atk';
      // Using atkSort helps toggle the order (a-z || z-a)
      if(this.atkSort !== 1) {
        this.filteredList.sort((a, b) => b.attack - a.attack);
      } else {
        this.filteredList.sort((a, b) => a.attack - b.attack);
      }
        this.atkSort = -this.atkSort;
    },

    sortDef() {
      this.sortStyle = 'def';
      // Using defSort helps toggle the order (a-z || z-a)
      if(this.defSort !== 1) {
        this.filteredList.sort((a, b) => b.defense - a.defense);
        } else {
          this.filteredList.sort((a, b) => a.defense - b.defense);
        }
          this.defSort = -this.defSort;
    },

    filterAtk(minAtk) {
      this.filterStyle = 'atk';
      // masterList used to store current list to revert back to
      if(this.masterList != this.filteredList) {
        this.filteredList = this.masterList;
      }
      this.filteredList = this.filteredList.filter(a => a.attack >= minAtk);
    },

    filterDef(minDef) {
      this.filterStyle = 'def';
      // masterList used to store current list to revert back to
      if(this.masterList != this.filteredList) {
        this.filteredList = this.masterList;
      }
      this.filteredList = this.filteredList.filter(a => a.defense >= minDef);
    }
  },

  // COMPUTED
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
@keyframes ball-zoom {
  from {
    transform: scale(1);
  } to {
    transform: scale(1.5);
  }
}

@keyframes ball-unzoom {
  from {
    transform: scale(1.5);
  } to {
    transform: scale(1);
  }
}


#app {
  display: flex;
  flex-direction: column;
  border-top: 3px solid gray;
  border-right: 3px solid black;
  border-bottom: 3px solid black;
  border-left: 3px solid gray;
  background-color: bisque;
  width: fit-content;
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

img {
  align-self: center;
  cursor: pointer;
  animation: ball-unzoom 500ms forwards;
}

img:hover {
  animation: ball-zoom 1s forwards;
}

#atk-def {
  display: flex;
  justify-content: space-between;
  padding: 6px;
  background: black;
  color: white;
  /* border: 1px solid red; */
}

#results {
  padding: 13px;
}

</style>
