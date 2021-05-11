<template>
<h1>Youtube Browser</h1>
  <SearchBar @inputChange="searchVideo"/>
  <VideoList :videos="list"/>
</template>

<script>
import axios from "axios";
import SearchBar from './components/SearchBar.vue';
import VideoList from './components/VideoList.vue';
import {API_KEY}from "./private.js";


export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList
  },

  data(){

    return {
      list: []
    }

  },

  methods: {
    searchVideo(input) {
      console.log(input);
      axios.get("https://www.googleapis.com/youtube/v3/search", {
        params:{
          key:API_KEY,
          type:"video",
          part: "snippet",
          q: input 
        }

      }).then((response)=> {
          this.list=response.data.items;
          console.log(this.list);
      });

    },

  }



}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
