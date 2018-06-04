<template>
<div id="atk-def">
    <label>
    Min-Atk:
    <input
        type="number"
        v-model.number="minatk"
        @change="$emit('minatk', minatk)"
    /></label>
</div>
</template>

<script>
export default {
    data() {
        return {
            minatk: 0
        }
    }

}
</script>

<style>

</style>
