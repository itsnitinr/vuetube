<template>
  <li>{{ video.snippet.title }}</li>
</template>

<script>
export default {
  name: "VideoItem",
  props: ["video"],
};
</script>