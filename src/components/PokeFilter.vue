<template>
  <div class="filter">
    
    <div id="input-div">
      <input id="hp-input" type="number" placeholder="Minimum HP" v-model.number="filtered.hp"> 
    </div>
    <TypeButton 
      v-for="n in types"
      :key="n"
      :types="n"
      :filtered="filtered"
      @select="filterByType"/> 
  </div>
</template>

<script>
import TypeButton from './TypeButton';

export default {
  data() {
    return {
      filterBy: [],
    }
  },
  props: ['filtered', 'types'],
  components: {
    TypeButton
  },
  methods: {
    filterByType(types) {
      this.filtered.type = types;     
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.filter {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  padding-top: 63px;
  padding-left: 30px;
  margin-top: 30px;
  width: 561px; 
  height: 100px;
}

#hp-input {
  position: absolute;
    right: 170px;
    top: 126px;
  font-size: 20px;
  padding: 5px 10px 5px 5px;
  width: 140px;
}

</style>
