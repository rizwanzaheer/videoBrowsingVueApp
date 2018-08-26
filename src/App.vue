<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome Rizwan, In Vue.js App "/> -->
    <SearchBar />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import SearchBar from "./components/SearchBar.vue";

export default {
  name: "app",
  components: {
    // HelloWorld,
    SearchBar
  }
};
</script>

<style>
/* #app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
