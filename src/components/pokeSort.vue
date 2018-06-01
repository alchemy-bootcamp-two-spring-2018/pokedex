<template>
<div id="sort">
    <ul>
        <li @click="$emit('name')">Name</li>
        <li @click="$emit('type')">Type</li>
        <li @click="$emit('atk')">Atk</li>
        <li @click="$emit('def')">Def</li>
    </ul>
</div>
</template>

<script>
export default {

}
</script>

<style scoped>
#sort, ul, li {
    padding: 0;
    margin: 0;
}

li {
    flex-wrap: wrap;
    padding: 6px;
    border-top: 1px solid gray;
    border-left: 1px solid black;
    border-bottom: 1px solid black;
    border-left: 1px solid gray;
    background-color: aqua;
    list-style: none;
}

li:hover {
    cursor: pointer;
    background-color: aquamarine;
}
</style>
