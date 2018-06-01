<template>
    <div id="main">
        <h1>Manipulate your poke search!</h1>
        <button @click="$emit('all')">ALL</button>
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
        </div>
    </div>
</template>


<script>
import filter from './Filter.vue'

export default {
    props: ['pokeList'],
    components: {
        filter
    }
}
</script>

<style>

</style>
