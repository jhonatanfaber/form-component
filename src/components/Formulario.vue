<template>
  <div>
      <custom-input v-if="name" v-model="myResult.name" type="text">Nombre:</custom-input>
      <custom-input v-if="tel" v-model="myResult.tel" type="tel">Telefono:</custom-input>
      <custom-input v-if="email" v-model="myResult.email" type="email">Correo:</custom-input>
      <custom-input v-if="username" v-model="myResult.username" type="text">Usuario:</custom-input>
      <custom-input v-if="pass" v-model="myResult.pass" type="password">Contraseña:</custom-input>
      <custom-input v-if="verifyPass" v-model="myResult.verifyPass" type="password">Confirma la contraseña:</custom-input>
      <button @click="check">Send</button>
  </div>
</template>

<script>
import CustomInput from "./CustomInput"
export default {
    "name": "auto-form",
    "components": {
        CustomInput
    },
    data() {
        return {
            myResult: {name: "ruben",
            tel: "666999555",
            email: "ruben@gmail.com",
            username: "ruben123",
            pass: "pass1234",
            verifyPass: "pass1234"},
            checks: checks
        }
    },
    "props": [ "result", "name", "tel", "email", "username", "pass", "verifyPass" ],
    methods: {
        check() {
            console.log("compruebo las cosas", this.myResult);
            for(let p in this.myResult ) {
                if( this.checks[p](this.myResult[p], this) ) this.result[p] = this.myResult[p];
                else console.error("Error al verificar la propiedad", p);
            }
            this.$emit("completed");
        }
    } 
}

var checks = {};
let regexmail = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
checks.name = function(name) { return name.length > 1 && name.length < 20 && name.match(/^[a-z ,.'-]+$/i) };
checks.tel = function(tel) { console.log("tel", tel); return tel.match(/^\d{9}$/) };
checks.email = function(email) { console.log("email check", email.match(regexmail)); return email.match(regexmail); };
checks.username = function(username) { return username.length > 0 && username.length < 20 && username.match(/\w/gi) };
checks.pass = function(pass) { return pass.length > 6 && pass.length < 20 };
checks.verifyPass = function(_, that) { return that.myResult.pass === that.myResult.verifyPass };
</script>

<style scoped>

</style>
