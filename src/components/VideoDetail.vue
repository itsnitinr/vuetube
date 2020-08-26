<template>
  <div v-if="video" class="video-detail">
    <div class="video-container">
      <iframe class="video-player" :src="videoUrl" />
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
  margin-top: 20px;
  padding: 1rem;
  border: 2px solid #303030;
  max-width: 100%;
}

.video-container {
  position: relative;
  overflow: hidden;
  width: 100%;
  padding-top: 56.25%;
}

.video-player {
  position: absolute;
  height: 100%;
  width: 100%;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
</style>