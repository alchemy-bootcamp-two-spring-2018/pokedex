<template>
  <div id="filter">
    <h1>Hello?</h1>
      <!-- <select>
          <option v-for="pokes in pokeList" :key="pokes.id" @select="$emit('change', pokes.type_1)">{{ pokes.type_1 }}</option>
      </select> -->
      <ul>
          <li v-for="pokes in pokeList" :key="pokes.id" @click="$emit('change', pokes.type_1)">{{ pokes.type_1 }}</li>
      </ul>
  </div>
</template>

<script>

export default {
  props: ['pokeList']
}
</script>
