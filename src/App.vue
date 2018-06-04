<template>
  <div id="app">
    <h1>Manipulate your poke search!</h1>
    <img src="./assets/ball.png" @click="displayAll">
    <div id="app-main">
      <poke-header id="header"
        :pokeList="remDupes"
        :notBlank="notBlank"
        @change="filterTypes"
        @name="sortName"
        @type="sortType"
        @atk="sortAtk"
        @def="sortDef"
        @minatk="filterAtk"
        @mindef="filterDef"
      />
      <poke-results id="results"
        v-if="notBlank"
        :banana="filteredList"
        @pokeTile="zoomin"
      />
      <div v-else>
        <h1>Please select a Pokemons</h1>
      </div>
    </div>

    <transition name="fade" mode="in-out">
      <poke-zoom id="poke-zoom"
        :zoom="zoom"
        :poke="this.poke"
        @zoomout="zoomout"
        v-if="zoom"
      />
    </transition>
</div>
</template>

<script>
import PokeHeader from './components/PokeHeader.vue'
import PokeResults from './components/PokeResults.vue'
import PokeZoom from './components/PokeZoom.vue'
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
      mindef: 0,
      zoom: false,
      notBlank: false,
      poke: ''
    }
  },

  // COMPONENTS
  components: {
    PokeHeader,
    PokeResults,
    PokeZoom
  },

  // METHODS
  methods: {
    zoomin(poke) {
      this.poke = poke
      this.zoom = true;
    },
    zoomout() {
      this.zoom = false;
    },

    sortTypes(pokeType) {
      // Make sure sorting options persist through type changes
      switch(this.sortStyle) {
        case'name':
          this.nameSort = -this.nameSort;
          this.sortName();
          break;
        case'type':
          this.typeSort = -this.typeSort;
          this.sortType();
          break;
        case'atk':
          this.atkSort = -this.atkSort;
          this.sortAtk();
          break;
        case'def':
          this.defSort = -this.defSort;
          this.sortDef();
          break;
      }
    },

    filterTypes(pokeType) {
      this.notBlank = true;
      this.filteredList = pokeList.filter(a => a.type_1 === pokeType);
      // tempList used to revert back from any array mutations
      this.masterList = this.filteredList;
      switch(this.filterStyle) {
        case('atk'):
          this.filterAtk(this.minatk);
          break;
        case('def'):
          this.filterDef(this.mindef);
          break;
      }
      this.sortTypes(pokeType);
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
      this.minatk = minAtk;
      // masterList used to store current list to revert back to
      if(this.masterList != this.filteredList) {
        this.filteredList = this.masterList;
      }
      this.filteredList = this.filteredList.filter(a => a.attack >= minAtk);
      this.sortTypes();
    },

    filterDef(minDef) {
      this.filterStyle = 'def';
      this.mindef = minDef;
      // masterList used to store current list to revert back to
      if(this.masterList != this.filteredList) {
        this.filteredList = this.masterList;
      }
      this.filteredList = this.filteredList.filter(a => a.defense >= minDef);
      this.sortTypes();
    }
  },

  // COMPUTED
  computed: {
    remDupes() {
      return this.pokeList.filter((obj, pos, arr) => {
          return this.pokeList.map(mapObj => mapObj.type_1).indexOf(obj.type_1) === pos;
      });
    },
    // Calculates the min and max attack and defense of all
    minAtk() {
      return this.filteredList.concat().sort((a, b) => b.attack - a.attack)[0];
    },
    maxAtk() {
      return this.filteredList.concat().sort((a, b) => a.attack - b.attack)[0];
    },
    minDef() {
      return this.filteredList.concat().sort((a, b) => b.defense - a.defense)[0];
    },
    maxDef() {
      return this.filteredList.concat().sort((a, b) => a.defense - b.defense)[0];
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
  margin: auto;
  flex-direction: column;
  border-top: 3px solid gray;
  border-right: 3px solid black;
  border-bottom: 3px solid black;
  border-left: 3px solid gray;
  background-color: slategrey;
  width: fit-content;
  background-image: url('assets/thread.png');
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
  margin: 6px;
  height: 350px;
  overflow: auto;
  border-top: 3px solid black;
  border-right: 3px solid gray;
  border-bottom: 3px solid gray;
  border-left: 3px solid black;
  background-color: darkcyan;
  background-image: url('assets/paper.png');
}

#poke-zoom {
  position: fixed;
  display: inline-flex;
  width: 600px;
  height: 100%;
  animation: fade-in 500ms forwards;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
