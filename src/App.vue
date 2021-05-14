<template>
  <div class="app">
    <Navbar />
    <SearchBar @inputChange="searchVideo" />
    <VideoList :videos="list" />
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar.vue";
import VideoList from "./components/VideoList.vue";
import Navbar from "./components/NavBar.vue";
import { API_KEY } from "./private.js";

export default {
  name: "App",
  components: {
    SearchBar,
    VideoList,
    Navbar,
  },

  data() {
    return {
      list: [],
    };
  },

  methods: {
    searchVideo(input) {
      console.log(input, this.list);
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: input,
          },
        })
        .then((response) => {
          this.list = response.data.items;
          console.log(this.list);
        });
    },
  },
};
</script>

<style>
.app {
  width: 80%;
  margin: 2% auto;
}
</style>
