<template>
    <div id="poke">
        <div v-for="poke in banana" :key="poke.id">
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

<style>
img {
    height: 50px;
    width: 50px;
}
</style>
