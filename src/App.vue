<script setup>
import Desktop from './components/Desktop.vue';
import Taskbar from './components/Taskbar.vue';
import DeskClock from './components/DeskClock.vue';
</script>

<template>
  <DeskClock />
  <Desktop />
  <Taskbar />
</template>

<style>
body {
  background-image: url("https://4kwallpapers.com/images/wallpapers/big-sur-mountains-night-dark-macos-big-sur-stock-california-6016x6016-1493.jpg");
  background-size: cover;
}

* {
  -webkit-user-select: none;
  user-select: none;
  box-sizing: border-box;
  font-family: "IBM Plex Sans", sans-serif;
  margin: 0;
  padding: 0;
}
</style>