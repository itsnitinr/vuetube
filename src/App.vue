<template>
  <div>
    <Searchbar @termChange="onTermChange"></Searchbar>
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
