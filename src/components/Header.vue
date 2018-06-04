<template>
  <div class="headerContainer">
    <section>
      <Sort
      :sort="sort"
      />
    </section>
    <section>
      <SearchFilter
      :filter="filter"
      />
    </section>
  </div>
</template>

<script>
import SearchFilter from './SearchFilter.vue';
import Sort from './Sort.vue';

export default {
  props: {
    filter: Object,
    sort: Object,
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
