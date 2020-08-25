<template>
  <ul>
    <VideoItem v-for="video in videos" :key="video.etag" :video="video" />
  </ul>
</template>

<script>
import VideoItem from "./VideoItem";

export default {
  name: "VideoList",
  components: {
    VideoItem,
  },
  props: {
    videos: Array,
  },
};
</script>

<style>
ul {
  color: white;
  list-style: none;
}
</style>