<template>
<div id="poke">
    <transition name="fade">
    <result
        v-for="poke in list"
        :key="poke.pokemon"
        :pokemon="pokemon"
        :onZoom="onZoom"
    />
    </transition>
</div>
</template>

<script>
import result from './result.vue'
export default {
    props: {
        list: Object,
        onZoom: {
            type: Function,
            required: true
        }
    },
    components: {
        result
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