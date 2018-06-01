<template>
<div id="filter">
    <ul>
        <li v-for="pokes in pokeList" :key="pokes.id" @click="$emit('change', pokes.type_1)">{{ pokes.type_1 }}</li>
    </ul>
</div>
</template>

<script>
export default {
    props: ['pokeList']
}
</script>

<style>
li {
    list-style: none;
}

li:hover {
    cursor: pointer;
    background-color: aquamarine;
}
</style>
