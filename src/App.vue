<template>
  <div id="app">

    <section>
      <Header :filter="filter" :sort="sort"/>
    </section>

    <section>
      <Results :pokemonList="sorted" :filter="filter.type"/>   
    </section>

  </div>
</template>

<script>

import Header from './components/Header.vue';
import Results from './components/Results.vue';
import pokemon from '../pokemon.js';

export default {
  data() {
    return {
      pokeList: pokemon,

      filter: {
        type: '',
        hp: ''
      },

      sort: {
        by: ''
      }
    };
  },

  computed: {
    filtered() {
      return this.pokeList.filter(pokemon => {
        if(this.filter.type === 'All') {
          return (this.pokeList)
          && (pokemon.hp === '' || pokemon.hp >= this.filter.hp);
        }
        return (pokemon.type_1 === '' || pokemon.type_1 === this.filter.type)
        && (pokemon.hp === '' || pokemon.hp >= this.filter.hp)
      });
    },

     sorted() {
      if(this.sort.by === '') {
        return this.filtered;
      }

      else if(this.sort.by === 'HP') {
        return this.filtered.slice().sort((a, b) => a.hp - b.hp);
      }

      else if(this.sort.by === "Type") {
         return this.filtered.slice().sort((a, b) => {
          const x = a.type_1.toLowerCase();
          const y = b.type_1.toLowerCase();
          if(x < y) {return -1};
          if(x > y) {return 1};
          return 0;
        });
      }

      else {
        return this.filtered.slice().sort((a, b) => {
          const x = a.pokemon.toLowerCase();
          const y = b.pokemon.toLowerCase();
          if(x < y) {return -1};
          if(x > y) {return 1};
          return 0;
        });
      }
     }
  },

  components: {
    Header,
    Results
  }
};

</script>

<style>

</style>
