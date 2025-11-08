<script setup>
import { Icon } from "@iconify/vue";
import { ref, onMounted } from "vue";

const clock = ref("");

onMounted(() => {
  setInterval(() => {
    clock.value = new Date()
      .toLocaleTimeString()
      .replace(":", "h")
      .slice(0, 5);
  }, 1000);
});
</script>

<template>
  <nav class="taskbar">
    <div class="taskbar-start">
      <Icon icon="pixelarticons:track-changes" class="icon" />
      <div class="launcher">
        <Icon icon="pixelarticons:folder" class="icon" />
        <Icon icon="pixelarticons:github" class="icon" />
        <Icon icon="pixelarticons:video" class="icon" />
      </div>
    </div>
    <div class="taskbar-end">
      <Icon icon="pixelarticons:download" class="icon" />
      <Icon icon="pixelarticons:radio-signal" class="icon" />
      <Icon icon="pixelarticons:bluetooth" class="icon" />
      <Icon icon="pixelarticons:pin" class="icon" />
      <Icon icon="pixelarticons:volume-3" class="icon" />
      <span class="clock">{{ clock }}</span>
    </div>
  </nav>
</template>

<style scoped>
.taskbar {
  justify-content: space-between;
  background-color: #0f0f0f;
  width: calc(100vw - 2.4em);
  flex-direction: row;
  border-radius: .5em;
  position: absolute;
  padding: .2em .7em;
  margin: 1em 1.2em;
  height: 3em;
  bottom: 0;
}

.taskbar,
.launcher,
.taskbar-start,
.taskbar-end {
  display: flex;
  align-items: center;
}

.launcher {
  margin-left: 1rem;
  gap: .5em;
}

.icon {
  font-size: 2.1rem;
  transition: filter 100ms ease-in-out;
}

.icon:hover {
  filter: drop-shadow(0 0 2px #ffffff80);
  transition: filter 100ms ease-in-out;
}

.taskbar-end {
  gap: .5em;
}

.taskbar-end .icon {
  font-size: 1.4rem;
}

.clock {
  padding-left: .3em;
  padding-bottom: .05em;
  padding-right: .15em;
  font-weight: 250;
  font-size: 1.6em;
}
</style>