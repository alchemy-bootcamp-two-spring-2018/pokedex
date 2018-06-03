<template>
<div id="atk-def">
    <label>
    Min-Def: 
    <input
        type="number"
        v-model.number="mindef"
        @change="$emit('mindef', mindef)"
    /></label>
</div>
</template>

<script>
export default {
    data() {
        return {
            mindef: 0
        }
    }

}
</script>

<style>

</style>
