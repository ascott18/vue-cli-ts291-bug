<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from './components/HelloWorld.vue';

import { BaseFoo } from './imported-class'
import * as Consts from './imported-const'

class DerivedFoo extends BaseFoo<any> {
  constructor() { super(Consts.Foo) }
}

export default Vue.extend({
  name: 'app',
  components: {
    HelloWorld
  },
  mounted() {
    var fooInstance = new DerivedFoo()
  }
});
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
