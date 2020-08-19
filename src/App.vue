<template>
  <div>
    <Searchbar @termChange="onTermChange"></Searchbar>
  </div>
</template>

<script>
import Searchbar from "./components/Searchbar";

export default {
  name: "App",
  components: {
    Searchbar,
  },
  methods: {
    onTermChange(searchTerm) {
      console.log(searchTerm);
    },
  },
};
</script>
