<template>
  <div><slot></slot>
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

</style>
