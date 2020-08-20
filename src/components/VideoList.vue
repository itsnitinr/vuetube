<template>
  <ul>
    VideoList
    {{ videos.length }}
  </ul>
</template>

<script>
export default {
  name: "VideoList",
  props: {
    videos: Array,
  },
};
</script>

<style>
</style>