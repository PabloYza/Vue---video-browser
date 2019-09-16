<template>
  <ul>
    VideoList
    {{ myVideos.length }}
  </ul>
</template>


<script>
export default {
  name: 'VideoList',
  props: ['myVideos']
};
</script>


<style>

</style>