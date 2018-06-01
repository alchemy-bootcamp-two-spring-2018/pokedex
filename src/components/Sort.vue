<template>
  <span>
    <h3>This is our Pokedex SORT component!</h3>
    <ul>
      <li>Name</li>
      <li>Type 1</li>
      <li>Attack</li>
      <li>Defense</li>

    </ul>
  </span>
</template>

<script>

export default {

  props: ['sortedByName', 'sortedByType']

};

</script>


<style>

</style>