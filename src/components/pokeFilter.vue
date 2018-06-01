<template>
<div id="filter">
    <ul>
        <li
            :style="{ backgroundColor: pokes.color_1 }"
            v-for="pokes in pokeList"
            :key="pokes.id"
            @click="$emit('change', pokes.type_1)"
            >
            {{ pokes.type_1 }}
        </li>
    </ul>
</div>
</template>

<script>
export default {
    props: ['pokeList']
}
</script>

<style scoped>

ul {
    display: flex;
    flex-wrap: wrap;
}

li {
    margin: 3px;
    display: inline;
    flex-wrap: wrap;
    padding: 6px;
    border-top: 1px solid gray;
    border-left: 1px solid black;
    border-bottom: 1px solid black;
    border-left: 1px solid gray;
    border-radius: 3px;
    box-shadow: 1px 1px 1px black;
    list-style: none;
}

li:hover {
    cursor: pointer;
}
</style>
