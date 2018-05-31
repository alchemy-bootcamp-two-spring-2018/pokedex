<template>
    <div class="tiles">
        <h1>
            {{pokemonTile.pokemon}}
         </h1>
    </div> 
</template>

<script>


    export default {
        data() {
            return {
            }
        },
        props: ['pokemonTile']
    }
</script>