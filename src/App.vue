<template>
  <div>
    <Searchbar @termChange="onTermChange"></Searchbar>
  </div>
</template>

<script>
import axios from "axios";
import Searchbar from "./components/Searchbar";
const API_KEY = "AIzaSyB-2PzOea7T4smeCg32rXbGn1rTFA_otEA";

export default {
  name: "App",
  components: {
    Searchbar,
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
        .then((res) => console.log(res));
    },
  },
};
</script>
