<template>
    <div class="tiles">
        <h1>
            {{pokemonTile.pokemon}}
         </h1>
         <img :src="pokemonTile.url_image">
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
<style>
.tiles  img {
    width: 60px;
    height: 60px;
}
.tiles {
    background: wheat;
    width: 125px;
    
}
</style>