<template>
  <div class="headerContainer">
    <section>
      <Sort/>
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
    data () {
      return {
        filter: {
          type: ''
        }
      }
    },
  components: {
    SearchFilter,
    Sort
  }

}
</script>

<style>
section.header {
  display: inline-block;
}

</style>
