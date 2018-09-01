<template>
  <ul class="list-group">
    <VideoListItem
     v-for="video in videos"
     :key="video.etag"
     :video="video"
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
