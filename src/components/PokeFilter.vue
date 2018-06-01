<template>
  <div class="filter">
    <h2>Filter</h2>
    <button @click="filterByNormal">normal</button>
    <button @click="filterByWater">water</button>
    <button @click="filterByFire">fire</button>
    <button @click="filterByFighting">fighting</button>
    <button @click="filterByFlying">flying</button>
    <button @click="filterByGrass">grass</button>
    <button @click="filterByPoison">poison</button>
    <button @click="filterByElectric">electric</button>
    <button @click="filterByGround">ground</button>
    <button @click="filterByPsychic">psychic</button>
    <button @click="filterByRock">rock</button>
    <button @click="filterByIce">ice</button>
    <button @click="filterByBug">bug</button>
    <button @click="filterByDragon">dragon</button>
    <button @click="filterByGhost">ghost</button>
    <button @click="filterByDark">dark</button>
    <button @click="filterBySteel">steel</button>
    <button @click="filterByFairy">fairy</button>
    
  </div>
</template>

<script>
import Element from './Element';

export default {
  data() {
    return {
      elementList: ['water', 'normal', 'fire', 'fighting', 'flying', 'grass', 'poison', 'electric', 'ground', 'psychic', 'rock', 'ice', 'bug', 'dragon', 'ghost', 'dark', 'steel', 'fairy']
    }
  },
  props: ['filtered'],
  components: {
    Element
  },
  methods: {
    filterByWater() {
      this.filtered.type = 'water';
    },
    filterByNormal() {
      this.filtered.type = 'normal';
    },
    filterByFire() {
      this.filtered.type = 'fire';
    },
    filterByFighting() {
      this.filtered.type = 'fighting';
    },
    filterByFlying() {
      this.filtered.type = 'flying';
    },
    filterByGrass() {
      this.filtered.type = 'grass';
    },
    filterByPoison() {
      this.filtered.type = 'poison'; 
    },
    filterByElectric() {
      this.filtered.type = 'electric';
    },
    filterByGround() {
      this.filtered.type = 'ground';
    },
    filterByPsychic() {
      this.filtered.type = 'psychic';
    },
    filterByRock() {
      this.filtered.type = 'rock';
    },
    filterByIce() {
      this.filtered.type = 'ice';
    },
    filterByBug() {
      this.filtered.type = 'bug';
    },
    filterByDragon() {
      this.filtered.type = 'dragon';
    },
    filterByGhost() {
      this.filtered.type = 'ghost';
    },
    filterByDark() {
      this.filtered.type = 'dark';
    },
    filterBySteel() {
      this.filtered.type = 'steel';
    },
    filterByFairy() {
      this.filtered.type = 'fairy';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
