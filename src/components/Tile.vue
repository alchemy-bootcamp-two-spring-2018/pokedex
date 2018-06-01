<template>
    <div class="tiles">
        <h1>
            {{pokemon.pokemon}}
         </h1>
         <img :src="pokemon.url_image">
    </div> 
</template>

<script>
    export default {
        data() {
            return {
            }
        },
        props: ['pokemon']
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