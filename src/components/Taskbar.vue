<script setup>
import { Icon } from "@iconify/vue";
import { ref, onMounted } from "vue";

const clock = ref("00h00");

onMounted(() => {
  const updateTime = () => {
    clock.value = new Date()
      .toTimeString()
      .replace(":", "h")
      .slice(0, 5);
  };

  updateTime();
  setInterval(updateTime, 1000);
});
</script>

<template>
  <nav class="taskbar">
    <div class="taskbar-start">
      <Icon icon="ci:main-component" class="icon" />
      <div class="launcher">
        <Icon icon="ci:folder" class="icon" />
        <Icon icon="ci:planet" class="icon" />
        <Icon icon="ci:camera" class="icon" />
      </div>
    </div>
    <div class="taskbar-end">
      <div class="tray-icons">
        <Icon icon="ci:download" class="icon" />
        <Icon icon="ci:wifi-high" class="icon" />
        <Icon icon="ci:volume-max" class="icon" />
      </div>
      <span class="clock">{{ clock }}</span>
      <Icon icon="ci:bell-notification" class="icon" />
    </div>
  </nav>
</template>

<style scoped>
.taskbar {
  justify-content: space-between;
  width: calc(100vw - 2.4em);
  flex-direction: row;
  position: absolute;
  padding: .2em .85em;
  margin: 0.8em 1.2em;
  height: 3em;
  bottom: 0;
  /* From https://css.glass */
  background: rgba(36, 36, 46, 0.31);
  border-radius: 1rem; /* 16px */
  box-shadow: 0 0.25rem 1.875rem rgba(0, 0, 0, 0.1); /* 4px 30px */
  backdrop-filter: blur(0.3125rem); /* 5px */
  -webkit-backdrop-filter: blur(0.3125rem);
  border: 0.0625rem solid rgba(36, 36, 46, 0.3); /* 1px */
}

.taskbar,
.launcher,
.tray-icons,
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
  font-size: 1.75rem;
  transition: filter 100ms ease-in-out;
}

.icon:hover {
  filter: drop-shadow(0 0 2px #ffffff80);
  transition: filter 100ms ease-in-out;
}

.tray-icons {
  gap: .5em;
}

.tray-icons .icon {
  font-size: 1.5rem;
}

.clock {
  padding-left: .6em;
  padding-bottom: .05em;
  padding-right: .6em;
  font-weight: 350;
  font-size: 1.5em;
}
</style>