<template>
  <div id="app">
    <Formulario
        :result="user"
        @completed="doThings"
        name="true"
        tel="true"
        email="true"
        username="true"
        pass="true"
        verifyPass="true"
        />
    <div>
      {{user}}
    </div>
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
  },
  methods: {
    doThings() {
      this.$forceUpdate();  // de momento
      console.log("Me ha devuelto", this.user);
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
