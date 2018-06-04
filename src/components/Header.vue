<template>
  <div class="headerContainer">
    <section>
      <Sort
      :chosenSort="chosenSort"
      />
    </section>
    <section>
      <SearchFilter
      :filter="pokeFilter"
      />
    </section>
  </div>
</template>

<script>
import SearchFilter from './SearchFilter.vue';
import Sort from './Sort.vue';

export default {

  props: {
    pokeFilter: Object,
    chosenSort: Object
  },
  components: {
    SearchFilter,
    Sort
  }

};
</script>

<style>
section.header {
  display: inline-block;
}

</style>
