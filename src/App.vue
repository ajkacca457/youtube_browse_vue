<template>
  <div class="app container justify-content-center">
    <Navbar />
    <SearchBar @inputChange="searchVideo" />
    <div class="row">
    <VideoDisplay :video="video"/>
    <VideoList :videos="list"  @videoselect="videodisplay"/>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar.vue";
import VideoList from "./components/VideoList.vue";
import Navbar from "./components/NavBar.vue";
import { API_KEY } from "./private.js";
import VideoDisplay from "./components/VideoDisplay.vue"

export default {
  name: "App",
  components: {
    SearchBar,
    VideoList,
    Navbar,
    VideoDisplay
  },

  data() {
    return {
      list: [],
      video:""
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

    videodisplay(video){
     this.video=video;
    }

  },
};
</script>

<style>
.app {
  width: 80%;
  margin: 2% auto;
}
</style>
