<template>
  <div>
    <div class="nav-header">
      <img src="@/assets/yt_logo_rgb_dark.png" alt />
      <Searchbar @termChange="onTermChange" />
      <span></span>
    </div>
    <div class="container">
      <VideoDetail :video="selectedVideo" />
      <VideoList :videos="videos" @videoSelect="onVideoSelect" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Searchbar from "./components/Searchbar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";

const API_KEY = "AIzaSyB-2PzOea7T4smeCg32rXbGn1rTFA_otEA";

export default {
  name: "App",
  components: {
    Searchbar,
    VideoList,
    VideoDetail,
  },
  data() {
    return { videos: [], selectedVideo: null };
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
    onVideoSelect(video) {
      this.selectedVideo = video;
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

.container {
  padding: 5rem;
  display: flex;
}

.container .video-detail {
  flex: 3;
}

.container .video-list {
  flex: 2;
}

@media (max-width: 700px) {
  .container {
    flex-wrap: wrap;
    justify-content: center;
  }
  .nav-header img {
    height: 20px;
  }
}
</style>