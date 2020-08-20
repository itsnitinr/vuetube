<template>
  <div>
    <div class="nav-header">
      <img src="@/assets/yt_logo_rgb_dark.png" alt />
      <Searchbar @termChange="onTermChange" />
      <span></span>
    </div>
    <VideoList :videos="videos" />
  </div>
</template>

<script>
import axios from "axios";
import Searchbar from "./components/Searchbar";
import VideoList from "./components/VideoList";

const API_KEY = "AIzaSyB-2PzOea7T4smeCg32rXbGn1rTFA_otEA";

export default {
  name: "App",
  components: {
    Searchbar,
    VideoList,
  },
  data() {
    return { videos: [] };
  },
  methods: {
    onTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm,
          },
        })
        .then((res) => (this.videos = res.data.items));
    },
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background: #181818;
  color: whitesmoke;
}

.nav-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background: #303030;
}

.nav-header img {
  height: 30px;
  fill: white;
}
</style>