<template>
    <div>
        <select v-model="srt.prop">
            <option value="pokemon">Name</option>
            <option value="type_1">Type</option>
            <option value="shape">Shape</option>
            <option value="attakc">Atk</option>
            <option value="defense">Def</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'srt',
    props: ['srt']
}
</script>

<style>

</style>
