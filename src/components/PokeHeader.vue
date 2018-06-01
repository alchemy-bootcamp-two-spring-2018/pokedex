<template>
    <div id="main">
        <h1>Manipulate your poke search!</h1>
        <button @click="$emit('all')">ALL</button>
        <div id="container">
            <pokeFilter id="filter"
                :pokeList="pokeList"
                @change="$emit('change', $event)"
            />
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

import pokeFilter from './pokeFilter.vue'
import pokeSort from './pokeSort.vue'

export default {
    props: ['pokeList'],
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
    text-align: left;
    width: 123px;
    background-color: gray;
}

#sort {
    text-align: left;
    width: 69px;
}
</style>
