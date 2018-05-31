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
}
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
  background: lightsteelblue;
  width: 90%;
  flex-grow: 2;
}

.results {
  background: lightsalmon;
  width: 90%;
  flex-grow: 5;
}
</style>
