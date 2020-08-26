<template>
  <ul class="video-list">
    <VideoItem
      v-for="video in videos"
      :key="video.etag"
      :video="video"
      @videoSelect="onVideoSelect"
    />
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
  methods: {
    onVideoSelect(video) {
      this.$emit("videoSelect", video);
    },
  },
};
</script>

<style>
ul {
  color: white;
  list-style: none;
}

@media (max-width: 700px) {
  ul {
    padding-inline-start: 0;
  }
}
</style>