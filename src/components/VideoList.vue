<template>
  <ul>
    <!-- " v-bind: " = " : " -->
    <VideoListItem
    v-for="video in myVideos"
    :video="video"
    :key="video.etag"
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
  props: ['myVideos']
};
</script>


<style>

</style>