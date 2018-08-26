<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <HelloWorld msg="Welcome Rizwan, In Vue.js App "/>
  </div>
</template>

<script>
import axios from "axios";
import HelloWorld from "./components/HelloWorld.vue";
import SearchBar from "./components/SearchBar.vue";
const API_KEY = "AIzaSyBDHxTtzOZM4d_0inRjfvyQc8YZh9T4O-k";

export default {
  name: "app",
  components: {
    HelloWorld,
    SearchBar
  },
  methods: {
    onTermChange: searchTerm => {
      console.log("searchTerm is: ", searchTerm);
      axios.get("https://www.googleapis.com/youtube/v3/search", {
        params: {
          key: API_KEY,
          type: "video",
          part: "snippet",
          q: searchTerm
        }
      }).then(data => {
        console.log('youtube response is: ', data);
      });
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
