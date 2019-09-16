<template>
  <div v-if="video" > <!-- conditional rendering statement - if truthy it will render the DIV / falsy it will not -->
    {{ video.snippet.title }}
  </div>

</template>


<script>
export default {
  name: 'VideoDetail',
  props: ['video'],

};
</script>


<style scoped>

</style>