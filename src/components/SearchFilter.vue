<template>
  <span class="menu">
    <p>Filter pokemon type:</p>
    <select v-model="filter.type">
      <option
      v-for="item in type"
      v-bind:key="item.index"
      >{{ getTitleCase(item) }}
      </option>
    </select>
    <p>Minimum attack:</p>
    <input type="number" v-model.lazy.number="filter.attack" id="attackInput"/>
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
p {
  margin: 10px;
  display: inline;
}

input {
  width: 50px;
}
</style>