<template>
  <span>
    <h3>This is our Pokedex FILTER component!</h3>
    Filter pokemon type:
    <select v-model="filter.type">
      <option
      v-for="item in type"
      v-bind:key="item.index"
      >{{ getTitleCase(item) }}
      </option>
    </select>

  </span>
</template>

<script>

export default {
  props: ['type', 'filter'],

  methods: {
    getTitleCase(str) {
      return str.toLowerCase().split(' ').map(function(word) {
        return (word.charAt(0).toUpperCase() + word.slice(1));
      }).join(' ');
    }
  }

};

</script>


<style>

</style>