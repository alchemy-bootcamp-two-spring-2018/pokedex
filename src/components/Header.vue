<template>
  <div class="headerContainer">
    <section>
      <Sort/>
    </section>
    <section>
      <SearchFilter/>
    </section>
  </div>
</template>

<script>
import SearchFilter from './SearchFilter.vue';
import Sort from './Sort.vue';

export default {
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
