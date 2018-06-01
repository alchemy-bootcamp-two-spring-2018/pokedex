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

<style>

</style>
