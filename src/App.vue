<template>
  <div id="app">
    <Formulario :result="user" name="true" tel="true"/>
  </div>
</template>

<script>
import Formulario from "./components/Formulario";

export default {
  name: "App",
  components: {
    Formulario
  },
  data() {
    return {
      user: {}
    }
  }
};
</script>

<style>
#app {
  display: grid;
  grid-template-columns: 1fr minmax(300px, 600px) 1fr;
}
#app>*{
  grid-column: 2/3;
}
</style>
