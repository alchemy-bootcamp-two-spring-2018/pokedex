<template>
  <div id="app">
    <h1>Pokedex!</h1>
    <main>
      <section class="header">
        <Header

        />
      </section>
      <section class="results">
        <Results
          
        />
      </section>
    </main>
    
  </div>
</template>

<script>

import Header from './components/Header.vue';
import Results from './components/Results.vue';

export default {

  components: {
    Header,
    Results
  }
};
</script>

<style>
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
  background: lightsalmon;
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
