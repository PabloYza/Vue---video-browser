<template>
  <ul class="list-group">
    <!-- " v-bind: " = " : " -->
    <VideoListItem
    v-for="video in myVideos"
    :video="video"
    :key="video.etag"
    @videoSelect="onVideoSelect"
    >
    </VideoListItem>
  </ul>
</template>


<script>
import VideoListItem from './VideoListItem';

export default {
  name: 'VideoList',
  components: {
    VideoListItem
  },
  methods: {
    onVideoSelect(video) {
      this.$emit('videoSelect', video);
    },
  },
  props: ['myVideos']
};
</script>


<style>

</style>