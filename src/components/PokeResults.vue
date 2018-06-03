<template>
    <div id="poke">
        <pokeTiles
            :banana="banana"
            @pokeTile="$emit('pokeTile', $event)"
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
