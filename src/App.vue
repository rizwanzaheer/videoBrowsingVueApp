<template>
  <div id="app" class="container">
    <img alt="Vue logo" src="./assets/logo.png">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList @videoSelect="onVideoSelect" :videos="videos"> </VideoList>
    {{ videos.length }}
    <HelloWorld msg="Welcome Rizwan, In Vue.js App "/>
  </div>
</template>

<script>
import axios from "axios";
import HelloWorld from "./components/HelloWorld.vue";
import SearchBar from "./components/SearchBar.vue";
import VideoList from "./components/VideoList.vue";

const API_KEY = "AIzaSyBDHxTtzOZM4d_0inRjfvyQc8YZh9T4O-k";

export default {
  name: "app",
  components: {
    HelloWorld,
    SearchBar,
    VideoList
  },
  data() {
    return {
      videos: []
    };
  },
  methods: {
    onTermChange(searchTerm) {
      console.log("searchTerm is: ", searchTerm);
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm
          }
        })
        .then(res => {
          console.log("this is: ", this);
          this.videos = res.data.items;
        });
    },
    onVideoSelect(video) {
      console.log("video is here: ", video);
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
