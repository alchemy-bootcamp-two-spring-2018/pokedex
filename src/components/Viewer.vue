<template>
  <section v-if="selectedPokemon" id="viewer">
    <h1>{{ selectedPokemon.pokemon }}</h1>
    <img :src="selectedPokemon.url_image">
  </section>
</template>

<script>

export default {
  props: ['selectedPokemon']
}

</script>

<style>
</style>