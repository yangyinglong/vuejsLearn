<template>
  <div id="app">
    <img src="./assets/logo.png">
    <p>HELLO, VUEJS</p>
    <!-- <ComputedVue />
    <WatchVue /> -->
    <IfElseVue />
    <FormVue />
  </div>
</template>

<script>

import ComputedVue from "./components/computedWatch/ComputedVue"
// import WatchVue from "./components/computedWatch/WatchVue"
import IfElseVue from "./components/ifElse/IfElseVue"
import FormVue from "./components/form/FormVue.vue"

export default {
  name: 'App',
  data() {
    return {
    }
  },
  components:{
    ComputedVue,
    // WatchVue
    IfElseVue,
    FormVue
  }
}
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
