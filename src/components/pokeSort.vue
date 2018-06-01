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
    border-top: 2px solid gray;
    border-right: 2px solid black;
    border-bottom: 2px solid black;
    border-left: 2px solid gray;
    margin: 1px;
    background-color: aqua;
    list-style: none;
}

li:hover {
    cursor: pointer;
    background-color: white;
}
</style>
