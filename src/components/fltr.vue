<template>
    <div>
        Type:
        <select v-mode="fltr.type">
            <option value="all">All</option>
            <option v-for="type in types" :key="type">
                {{ type }}
            </option>
        </select>

        Atk:
        <input v-model="fltr.atk" type="number">
        Def:
        <input v-model="fltr.def" type="number">
    </div>
</template>

<script>
export default {
    name: 'fltr',
    props: ['fltr', 'types']
}
</script>

<style>

</style>
