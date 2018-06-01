<template>
  <div class="tiles" v-bind:style="{background:pokemon.color_1}">
    <h3>
      {{pokemon.pokemon}}
    </h3>
    <img :src="pokemon.url_image">
  </div> 
</template>

<script>
  export default {
    data() {
      return {
    }
  },
  props: ['pokemon']
  }
</script>
<style>
  .tiles  img {
    width: 60px;
    height: 60px;
  }  
  .tiles {
    width: 125px;
    margin: 2px;

  }
</style>