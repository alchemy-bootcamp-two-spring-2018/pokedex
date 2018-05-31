<template>
  <div id="app">
    <title>Pokedex</title>
    <h1>This is our pokedex!</h1>
    <section class="header">
      <PokedexHeader/>
    </section>
    <section class="results"></section>
  </div>
</template>

<script>
import PokedexHeader from './components/PokedexHeader.vue';

export default {

  components: {
    PokedexHeader
  }
};

</script>

<style>


</style>
