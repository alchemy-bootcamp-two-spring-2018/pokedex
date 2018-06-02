<template>
  <div id="app">
    <h1>Pokedex</h1>
    <main>
      <section class="header">
        <Header
          :filter="filter"
          :sort="sort"
        />
      </section>
      <section class="results">
        <Results
          :list="filtered"
        />
      </section>
    </main>
    
  </div>
</template>

<script>
import pokemon from '../pokemon.js';
import Header from './components/Header.vue';
import Results from './components/Results.vue';

export default {
  data() {
    return {
      list: pokemon,
      sort: {
        property: 'id'

      },
      filter: {
        type: '',
      }
    };
  },

  computed: {
    sorted() {
      return this.filtered.slice().sort((a, b) => {
        console.log('propertyA', propertyA); 
        let propertyA = a[this.sort.property];
        let propertyB = b[this.sort.property];
        if(propertyA < propertyB) {
          return -1;
        }
        if(propertyA > propertyB) {
          return 1;
        }
        
        return 0;
        
      });

    },

    filtered() {
      let filteredPokemon = [];
      for(let i in this.list) {
        if(this.filter.type === '') {
          return filteredPokemon = this.list; 
        } else if(this.list[i].type_1 === this.filter.type) {
          filteredPokemon.push(this.list[i]);
        } 
      }
      return filteredPokemon;
    }

  },
  components: {
    Header,
    Results
  }
};

</script>

<style>
body {
  font-family: 'Avenir', sans-serif;
}
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background: #eee;
}

main {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 90%;
  margin: auto;
}

.header {
  display: flex;
  background: lightsteelblue;
  width: 90%;
 
}

.results {
  background: peachpuff;
  width: 90%;
  overflow-y: auto;
  height: 700px;

}
h1 {
  font-size: 5em;
    color: rgb(255, 247, 0);
    line-height: 1em;
    text-shadow: 3px 5px 1px rgb(12, 27, 168);
    -webkit-text-stroke-color: rgb(3, 12, 247);
    -webkit-text-stroke-width: 3px;
    margin-bottom: 20px;
    margin-top: 20px;
    text-align: center;
}
</style>
