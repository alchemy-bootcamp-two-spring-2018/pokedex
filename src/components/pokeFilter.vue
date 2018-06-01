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
    <div id="atk-def">
        Min-Atk:
        <input
            type="number"
            v-model.number="minAtk"
            @keypress="$emit('mindef', minAtk)"
        />
        Min-Def: 
        <input
            type="number"
            v-model.number="minDef"
            @keypress="$emit('mindef', minDef)"
        />
    </div>
</div>
</template>

<script>
export default {
    props: ['pokeList'],
    data() {
        return {
            minAtk: '',
            minDef: ''
        }
    }
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
    background-color: aqua;
    list-style: none;
}

li:hover {
    cursor: pointer;
    background-color: aquamarine;
}
</style>
