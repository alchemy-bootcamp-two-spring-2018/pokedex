<template>
  <section v-if="selectedPokemon" class="viewer">
    <img :src="selectedPokemon.url_image">
    <div id="viewer-content">
      <p>Name: {{ selectedPokemon.pokemon }}</p>
      <p>Type: {{ selectedPokemon.type_1 }} <span v-if="selectedPokemon.type_2 !== 'NA'">and {{ selectedPokemon.type_2 }}</span></p>
      <p>Height: {{ selectedPokemon.height / 10 }} m</p>
      <p>Weight: {{ selectedPokemon.weight / 10 }} kg</p>


    </div>
  </section>
  <section v-else>
    
  </section>
</template>

<script>

export default {
  props: ['selectedPokemon']
}

</script>

<style>
.viewer {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 30px;
  padding: 30px;
  background: greenyellow;
  border-radius: 25px;
  border: 1px solid black;
}
</style>