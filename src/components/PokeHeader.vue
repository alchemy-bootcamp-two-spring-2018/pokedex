<template>
    <div id="main">
        <h1>Manipulate your poke search!</h1>
        <button @click="$emit('all')">ALL</button>
        <div id="container">
            <!-- This is the arbitrary name we gave to our component on line ? -->
            <pokeFilter id="filter"
                :pokeList="pokeList"
                @change="$emit('change', $event)"
            />
            <!-- This is the arbitrary name we gave to our component on line ? -->
            <pokeSort id="sort"
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

<style>
#container {
    display: flex;
    flex-direction: row;

}

#filter {
    padding: 6px;
    text-align: left;
    width: 123px;
    background-color: gray;
}

#sort {
    padding: 6px;
    text-align: left;
    width: 69px;
}
</style>
