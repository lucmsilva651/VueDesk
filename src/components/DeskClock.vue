<script setup>
import { ref, onMounted } from "vue";

const hrs = ref("00"), min = ref("00");
const date = ref("No date information available");

onMounted(() => {
  const updateTime = () => {
    const now = new Date();
    hrs.value = String(now.getHours()).padStart(2, "0");
    min.value = String(now.getMinutes()).padStart(2, "0");
  };

  const updateDate = () => {
    date.value = new Date().toDateString();
  };

  updateTime();
  updateDate();

  setInterval(updateTime, 1000);
  setInterval(updateDate, 30 * 60000);
});
</script>

<template>
  <div class="middle-clock">
    <div class="clock">
      <span>{{ hrs }}</span>
      <span>{{ min }}</span>
    </div>
    <span>{{ date }}</span>
  </div>
</template>

<style scoped>
.middle-clock {
  transform: translate(-50%, -50%);
  position: absolute;
  left: 50%;
  top: 50%;
  gap: 1em;
}

.clock,
.middle-clock {
  flex-direction: column;
  text-align: center;
  line-height: 1;
  display: flex;
}

.clock span {
  font-size: 5.2em;
}
</style>