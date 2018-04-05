
# form-component Vuejs

## Description 

Vue Component that allows you to  create forms automatically.

![description](https://i.gyazo.com/31836e29c73a2dd4ba7484c29f3deefe.gif "descrpition")
```html
<template>
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
		this.$forceUpdate();
      	console.log("Completed!", this.user);
    }
  }
};
</script>

```
## Requirements

For development, you will only need Node.js installed on your environement.
And please use the appropriate [Editorconfig](http://editorconfig.org/) plugin for your Editor (not mandatory).

## Build Setup

```html
<!-- install dependencies -->
npm install
```

## Usage
```html
<formulario 
    :objeto="user" 
    @completed="signUp"
    email="true"
    username="true"
    tel="true"
    pass="true"
    verifyPass="true"
/>
```

## Installing

You can install this package by running the following command: npm install --save vue-Formulario

You can then import this package into your project using one of the following:
```js
import Formulario from './pathTo/Formulario'
```

## Authors

* **Borja Garcia** -  [GitHub](https://github.com/borjagarcia)
* **Ruben Vázquez** -  [GitHub](https://github.com/rubenvg95)
* **Ignacio Suarez** -  [GitHub](https://github.com/nacheting)
* **Jhonatan Faber** -  [GitHub](https://github.com/jhonanfaber)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

