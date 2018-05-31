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

</style>
