<template>
  <div>
    <ul>
      <li> {{ pokemon.pokemon }} </li>
      <li> HP: {{pokemon.hp}} </li>
      <li> Type: {{pokemon.type_1}} </li>
      <li> <img :src="pokemon.url_image"></li>
    </ul>
  </div>
</template>

<script>

export default {

  props: ['pokemon']

};

</script>

<style>
ul {
list-style: none;

}
img {
  width: 100px;
}
</style>