<template>
  <div>Soy un custom input {{value}}
      <input type="text" v-model="value" @change="update">
  </div>
</template>
<script>
export default {
  name: "custom-input",
  data() {
      return {
          value: ""
      }
  },
  methods: {
      update() {
          console.log("Cambios", this.value);
          this.$emit('changed123', this.value, "name");
      }
  }
}
</script>
<style scoped>

</style>
