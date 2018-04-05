<template>
  <div>
      <span><slot></slot></span>
      <input
      :type="type"
      v-bind:value="value"
      v-on:input="$emit('input', $event.target.value)"/>
  </div>
</template>
<script>
export default {
  name: "custom-input",
  props: ["value", "type"]
}
</script>
<style scoped>
div {
    display: grid;
    grid-template-columns: 30% 70%;
}
span {
    font-weight: bold;
}
</style>
