<template>
  <div v-if="video">
    <div class="video">
      <iframe :src="videoUrl" />
    </div>
    <div class="video-details">
      <h4>{{ video.snippet.title }}</h4>
      <p>{{ video.snippet.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: ["video"],
  computed: {
    videoUrl() {
      const { videoId } = this.video.id;
      return `https://www.youtube.com/embed/${videoId}`;
    },
  },
};
</script>

<style scoped>
.video-details {
  margin-top: 10px;
  padding: 1rem;
  border: 2px solid #303030;
}
</style>