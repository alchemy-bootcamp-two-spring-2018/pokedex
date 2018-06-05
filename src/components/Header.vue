<template>
    <div id="header-main">
        <srt
            :srt="srt"
        />
        <fltr
            :fltr="fltr"
        />
    </div>
</template>


<script>

// Imported components from the current folder
import srt from './srt'
import fltr from './fltr'

export default {
    // 'pokeList' was handed down from App.vue
    props: ['list'],
    // These are the arbitrary names we gave the components we imported on lines 2? & 2? (pokeFilter.vue & pokeSort.vue)
    components: {
        srt,
        fltr
    }
}
</script>

<style scoped>
</style>
