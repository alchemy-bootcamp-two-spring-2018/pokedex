<template>
  <span>
    <Sort :sort="sort"
    :order="order"
    />
    <SearchFilter
    :type="type"
    :filter="filter"
    />
  </span>
</template>

<script>
import Sort from './Sort.vue';
import SearchFilter from './SearchFilter.vue';

export default {
  props: ['type', 'filter', 'sort', 'order'],

  components: {
    Sort,
    SearchFilter,
  }
};

</script>

<style>

</style>
