<template>
    <div class="tiles">
        <h1 v-for="pokemon in list"
        v-bind:key="pokemon.pokemon">
        {{pokemon.pokemon}}
        </h1>
    </div> 
</template>

<script>
    import pokemon from '../pokemon.js';

    export default {
        data() {
            return {
                list: pokemon
            }
        }
    }
</script>