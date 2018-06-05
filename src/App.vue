<template>
  <div id="app">
    <!-- Zoom in of the user selected Pokemon -->
    <transition name="fade" mode="in-out">
      <zoom id="zoom"
        :poke="poke"
        @onZoom="zoom"
        v-if="zoomed"
      /> 
    </transition>
   

    <!-- Main Pokedex thing -->
    <div id="app-container">
      <h1>Manipulate your poke search!</h1>
      <img src="./assets/ball.png">
      <div id="app-main">

        <Header id="header"
          :types="types"
          :srt="srt"
          :fltr="fltr"
        />

        <Results id="results"
          :list="list"
          :onZoom="zoom"
        />
      </div>
    </div>
</div>
</template>

<script>
import Header from './components/Header'
import Results from './components/Results'
import Zoom from './components/Zoom'
import pokemon from './assets/pokemon'

export default {
  name: 'app',
  
  data() {
    return {
      pokemon,
      srt: {
        property: 'pokemon'
      },
      fltr: {
        type: 'all',
        atk: 0,
        def: 0
      },
      zoomed: false,
      poke: null
    }
  },

  // COMPONENTS
  components: {
    Header,
    Results,
    Zoom
  },

  // METHODS
  methods: {
    zoom: function(poke) {
      console.log('here?', poke);
      this.poke = poke;
      this.zoom = !this.zoom;
    }
  },

  // COMPUTED
  computed: {
    types() {
      return this.pokemon.filter((obj, pos) => {
          return this.pokemon.map(mapObj => mapObj.type_1).indexOf(obj.type_1) === pos;
      });
    },
    list() {
      return this.filtered.slice().sort((a, b) => {
        const elementA = a[this.sort.property];
        const elementB = b[this.sort.property];
        if(elementA === elementB) return 0;
        if(elementA > elementB) return 1;
        return -1;
      });
    },
    filtered() {
      const { type, atk, def } = this.filter;
      return this.pokemon.slice().filter(a => {
        type === 'all'
        || a.type_1 === 'type'
        && (atk < 1 || a.attack >= atk)
        && (def < 1 || a.defense >= def);
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
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
}

#app-container {
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
  width: 100%;
  height: 100%;
  animation: fade-in 500ms forwards;
  z-index: 99;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
