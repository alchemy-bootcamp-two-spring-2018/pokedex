<template>
<div id="poke">
    <transition name="fade">
    <pokeTiles
        :banana="banana"
        @pokeTile="$emit('pokeTile', $event)"
    />
    </transition>
</div>
</template>

<script>
import pokeTiles from './pokeTiles.vue'
export default {
    props: ['banana'],
    components: {
        pokeTiles
    }
}
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity .25s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>