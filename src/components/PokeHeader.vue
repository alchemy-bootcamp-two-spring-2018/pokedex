<template>
    <div id="main">
        <h1>Manipulate your poke search!</h1>
        <div id="filter">
            <select>
                <option v-for="pokes in pokeList" :key="pokes.id">{{ pokes.type_1 }}</option>
            </select>
        </div>
        <div id="sort">
            <select>
                <option>Name</option>
                <option>Type</option>
                <option>Atk</option>
                <option>Def</option>
            </select>
        </div>
    </div>
</template>


<script>

export default {
    props: ['pokeList'],
    methods: {
        remDupes() {
            // return this.pokeList.filter((el, i, arr) => arr.indexOf(el) === i);
        }
    }
}
</script>

<style>

</style>
