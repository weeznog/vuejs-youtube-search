<template lang="html">
  <ul class="list-group col-md-4">
    <VideoListItem v-for="video in videos" :key="video.etag" :video="video" @videoSelect="onVideoSelect"  />
  </ul>
</template>

<script>
import VideoListItem from "./VideoListItem";
export default {
  name: "VideoList",
  props: {
    // name from :videos
    videos: Array // typechecking
  },
  methods: {
    onVideoSelect(video) {
      this.$emit("videoSelect", video);
    }
  },
  components: {
    VideoListItem
  }
};
</script>

<style scoped>
</style>
