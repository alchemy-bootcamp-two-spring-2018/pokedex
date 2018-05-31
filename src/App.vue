<template>
  <div id="app">
    App area
    <section class="header">
      <HeaderArea/>
    </section>
    <section class="results">
      <ResultsViewer/>
    </section>
  </div>
</template>

<script>
import HeaderArea from './components/Header.vue';
import ResultsViewer from './components/Results.vue';

export default {
      components: {
      HeaderArea,
      ResultsViewer
    }
}

</script>

<style>

</style>
