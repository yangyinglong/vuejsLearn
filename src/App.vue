<template>
  <div id="app">
    <img src="./assets/logo.png">
    <p>HELLO, VUEJS</p>
    <!-- <ComputedVue />
    <WatchVue /> -->
  </div>
</template>

<script>

import ComputedVue from "./components/computedWatch/ComputedVue"
// import WatchVue from "./components/computedWatch/WatchVue"

export default {
  name: 'App',
  data() {
    return {
    }
  },
  components:{
    ComputedVue,
    // WatchVue
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
