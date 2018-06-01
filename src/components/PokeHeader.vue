<template>
    <div id="header-main">
        <div id="header-container">
            <!-- This is the arbitrary name we gave to our component on line ? -->
            <pokeFilter id="header-filter"
                :pokeList="pokeList"
                @change="$emit('change', $event)"
            />
            <!-- This is the arbitrary name we gave to our component on line ? -->
            <pokeSort id="header-sort"
                @name="$emit('name')"
                @type="$emit('type')"
                @atk="$emit('atk')"
                @def="$emit('def')"
            />
        </div>
    </div>
</template>


<script>

// Imported components from the current folder
import pokeFilter from './pokeFilter.vue'
import pokeSort from './pokeSort.vue'

export default {
    // 'pokeList' was handed down from App.vue
    props: ['pokeList'],
    // These are the arbitrary names we gave the components we imported on lines 2? & 2? (pokeFilter.vue & pokeSort.vue)
    components: {
        pokeFilter,
        pokeSort
    }
}
</script>

<style scoped>
#header-main {
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: row;
}

#header-container {
    display: flex;
    flex-direction: row;
    /* border: 1px solid red; */
}

#header-filter {
    padding: 6px;
    text-align: left;
    margin: auto;
    /* border: 1px solid red; */
}

#header-sort {
    padding: 6px;
    text-align: left;
    /* border: 1px solid red; */
}
</style>
