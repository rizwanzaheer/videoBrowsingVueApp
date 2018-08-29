<template>
  <ul>
    <li>
      Video List
    </li>
    <li>
      props length:{{ videos.length }}
    </li>

    <VideoListItem
     v-for="video in videos"
     v-bind:key="video.url"
     v-bind:video="video"
    >

    </VideoListItem>
  </ul>
</template>
<script>
import VideoListItem from "./VideoListItem";

export default {
  name: "VideoList",
  components: {
    VideoListItem
  },
  props: ["videos"]
  // props: {
  //   videos: Array
  // },
};
</script>
