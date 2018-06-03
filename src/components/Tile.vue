<template>
  <div class="tiles" 
    v-on:click="$emit('select', pokemon)"
    :style="{background:pokemon.color_1}">
    <h3>
      {{pokemon.pokemon}}
    </h3>
    <img :src="pokemon.url_image">
    <p>Type 1: {{pokemon.type_1}}</p>
    <p>Type 2: {{pokemon.type_2}}</p>
    <p>Defense: {{pokemon.defense}}</p>
    <p>Attack: {{pokemon.attack}}</p>
  </div> 
</template>

<script>
  export default {
  props: ['pokemon', 'select']
  }
</script>
<style>
  .tiles  img {
    width: 85px;
    height: 85px;
  }  
  .tiles p {
      font-size: 15px;
      margin: 1px;
  }
  .tiles {
    border-radius: 12px;
    width: 200px;
    max-height: 260px;
    margin: 2px;
    padding-bottom: 5px;
  }
  .tiles:hover {
    border-style: solid;
    border-width: 3px;
    border-color: red;
    cursor: pointer;
  }

</style>