<template>
  <div id="app">
    App area
    <section class="header">
      <HeaderArea/>
    </section>
    <section class="results">
      <ResultsArea/>
    </section>
  </div>
</template>

<script>
import HeaderArea from './components/Header.vue';
import ResultsArea from './components/Results.vue';

export default {
      components: {
      HeaderArea,
      ResultsArea
    }
}

</script>

<style>

</style>
