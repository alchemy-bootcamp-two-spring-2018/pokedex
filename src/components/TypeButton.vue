<template>
  <div class="type-button">
    <input type="checkbox"
      :id="types"
      :value="types"
      v-model="filtered.type"
      >
    <label :for="types">{{ types.replace(/^\w/, c => c.toUpperCase()) }}</label>
  </div>
</template>

<script>

export default {
  props: ['types', 'filtered']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.type-button {
 height: 42px;
 margin-bottom: 3px;
}

input {
  display: none;
}

input:checked ~ label {
  background-color: darkblue; 
}

label:hover {
  background-color: #F6BD20;
}

label {
  display: inline-block;
  cursor: pointer;
  width: 80.2px;
  height: 30px;
  padding: 6px 4px 4px 4px;
  background-color: #007BA7;
  color: white;
  text-align: center;
  font-size: 18px;
  border-radius: 2px;
  border: 2px solid black;
  margin: .6px;
  transition: all 0.5s;
  text-shadow: 0 0.07em 0.07em rgba(0,0,0,0.40);
  box-shadow: inset 0 -0.6em 0 -0.4em rgba(0,0,0,0.25);
}
</style>
