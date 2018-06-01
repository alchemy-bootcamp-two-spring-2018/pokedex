<template>
    <div id="poke">
        <pokeTiles
            :banana="banana"
        />
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
</style>
