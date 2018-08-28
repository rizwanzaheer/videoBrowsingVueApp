<template>
  <ul>
    <li>
      Video List
    </li>
    <li>
      props length:{{ videos.length }}
    </li>
  </ul>
</template>
<script>
export default {
  name: "VideoList",
  props: ["videos"]
  // props: {
  //   videos: Array
  // },
};
</script>
