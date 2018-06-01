<template>
  <div>
    <select class="pokemon-type">
      <option value="all">Select Type</option>
      <option value="water">Water</option>
      <option value="electric">Electric</option>
      <option value="ice">Ice</option>
    </select>
  </div>
</template>
<script>
  export default {

    props: ['filterOptions']
  }

</script>