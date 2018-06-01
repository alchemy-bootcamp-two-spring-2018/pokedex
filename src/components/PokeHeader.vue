<template>
    <div id="main">
        <h1>Manipulate your poke search!</h1>
        <button @click="$emit('all')">ALL</button>
<<<<<<< HEAD
        <div id="filter">
            <select>
                <option v-for="pokes in pokeList" :key="pokes.id" @select="$emit('change', pokes.type_1)">{{ pokes.type_1 }}</option>
            </select>
            <ul>
                <li v-for="pokes in pokeList" :key="pokes.id" @click="$emit('change', pokes.type_1)">{{ pokes.type_1 }}</li>
            </ul>
        </div>
        <div id="sort">
            <!-- <select>
                <option >Name</option>
                <option>Type</option>
                <option>Atk</option>
                <option>Def</option>
            </select> -->
            <ul>
                <li @click="$emit('name')">Name</li>
                <li @click="$emit('type')">Type</li>
                <li @click="$emit('atk')">Atk</li>
                <li @click="$emit('def')">Def</li>
            </ul>
=======
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
>>>>>>> 53809e5ae69b1628095476ec5b6365c10ad64b65
        </div>
    </div>
</template>


<script>
import filter from './Filter.vue'

// Imported components from the current folder
import pokeFilter from './pokeFilter.vue'
import pokeSort from './pokeSort.vue'

export default {
    // 'pokeList' was handed down from App.vue
    props: ['pokeList'],
<<<<<<< HEAD
    components: {
        filter
=======
    // These are the arbitrary names we gave the components we imported on lines 2? & 2? (pokeFilter.vue & pokeSort.vue)
    components: {
        pokeFilter,
        pokeSort
>>>>>>> 53809e5ae69b1628095476ec5b6365c10ad64b65
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
