<template>
  <li @click="onVideoSelect">
    <img :src="getThumbnailUrl" />
    <h3>{{ video.snippet.title }}</h3>
  </li>
</template>

<script>
export default {
  name: "VideoItem",
  props: ["video"],
  computed: {
    getThumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    },
  },
  methods: {
    onVideoSelect() {
      this.$emit("videoSelect", this.video);
    },
  },
};
</script>

<style scoped>
li {
  padding: 1.5rem;
  display: flex;
  align-items: flex-start;
  border: 2px solid #303030;
  cursor: pointer;
}
li:hover {
  background-color: #303030;
}
li img {
  margin-right: 1.5rem;
}
li h3 {
  font-size: 1.5rem;
}
</style>