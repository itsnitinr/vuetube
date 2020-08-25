<template>
  <div v-if="video" class="video-details">
    <h4>{{ video.snippet.title }}</h4>
    <p>{{ video.snippet.description }}</p>
  </div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: ["video"],
};
</script>

<style scoped>
.video-details {
  margin-top: 10px;
  padding: 1rem;
  border: 2px solid #303030;
}
</style>