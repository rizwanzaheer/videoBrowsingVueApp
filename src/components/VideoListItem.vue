<template>
  <li class="list-group-item media">
    <img :src="thumbnailUrl" alt="" class="mr-3">
   <div class="media-body">
    {{ video.snippet.title}}
   </div>
  </li>
</template>
<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    }
  }
};
</script>
