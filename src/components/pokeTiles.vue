<template>
<div id="tiles-main">
    <div v-if="banana.length === 0">
        <h1>No Pokemons to see here</h1>
    </div>
    <div class="pokes"
        v-else
        v-for="poke in banana"
        :key="poke.id"
        :style="{ backgroundColor: poke.color_1 }"
        >
        <h2>{{ poke.pokemon }}</h2>
        <img :src="poke.url_image">
        <ul>
            <li>Type: {{ poke.type_1 }}</li>
            <li>Attack: {{ poke.attack }}</li>
            <li>Defense: {{ poke.defense }}</li>
        </ul>
    </div>
</div>
</template>

<script>
export default {
    props: ['banana']
}
</script>

<style scpoed>
#tiles-main {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
}

.pokes {
    width: auto;
    padding: 6px;
    margin: 0;
    border-top: 2px solid gray;
    border-right: 2px solid black;
    border-bottom: 2px solid black;
    border-left: 2px solid gray;
}

ul {
    padding: 0;
}

li {
    text-align: center;
    list-style: none;
    display: flex;
    flex-direction: row;
    justify-content: center;
}

img {
    height: 69px;
    width: 69px;
}
</style>
