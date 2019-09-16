<template>
  <div class="container">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoDetail :video="selectedVideo" /> <!-- " v-bind: "  =   " : "   used to pass PROPS -->
    <VideoList :myVideos="videos" @videoSelect="onVideoSelect" ></VideoList>  <!-- " v-bind: "  =   " : "   used to pass PROPS -->
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";
const API_KEY = "AIzaSyAERlztz7MuiAY2IA_8nnQGUPoWrBIgwOU";


export default {
  name: "App",
  components: {
    SearchBar,
    VideoList,
    VideoDetail
  },
  data() {
    return {
      videos: [],
      selectedVideo: null

    };
  },
  methods: {
    onVideoSelect(video) {
      this.selectedVideo = video;
    },
    onTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet", // Specifies the data we want to bring
            q: searchTerm
          }
        })
        .then(response => {
          this.videos = response.data.items;
        })
        .catch(err => { console.log(err); })
    },
  }
};
</script>