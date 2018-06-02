<template>
  <span>
    Filter pokemon type:
    <select v-model="filter.type">
      <option
      v-for="item in type"
      v-bind:key="item.index"
      >{{ getTitleCase(item) }}
      </option>
    </select>

    Minimum attack:
    <input id="attackInput" type="number" v-model.lazy.number="filter.attack"/>

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