<template>
  <div>
      Holi {{result}}
      <custom-input v-if="name" @changed123="update" />
      <div v-if="tel">
        Esta tel
      </div>
  </div>
</template>

<script>
import CustomInput from "./CustomInput"
export default {
    "name": "auto-form",
    "components": {
        CustomInput
    },
    "props": [ "result", "name", "tel", "email", "username", "pass", "verifyPass" ],
    data() {
        return { invento: "" }
    },
    methods: {
        update(val, field) {
            console.log("s", val, field);
            this.result[field] = val;
        }
    }
}
</script>

<style scoped>

</style>
