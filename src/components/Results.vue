<template>
  <div>
    <h1>Results</h1>
  <div class="tile-area"> 
    <tiles/>
  </div>
  </div>
</template>

<script>
  import tiles from './Tile.vue';
  
  export default {
    components: {
      tiles
    }

  }
</script>

<style>
.tile-area {
  height: 500px;
  overflow: auto;
}
</style>