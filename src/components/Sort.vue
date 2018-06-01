<template>
  <span>
    <h3>This is our Pokedex SORT component!</h3>
    <select>
      <option
      v-for="item in type"
      v-bind:key="item.index"
      >{{ item }}
      </option>
    </select>

  </span>
</template>

<script>

export default {
  props: ['type'],

};

</script>


<style>

</style>