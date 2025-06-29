<script setup>
const online = ref(navigator?.onLine);

const updateOnlineStatus = () => {
  online.value = navigator.onLine;
  if (online.value) {
    window.location.reload();
  }
};

onMounted(() => {
  window.addEventListener("online", updateOnlineStatus);
  window.addEventListener("offline", updateOnlineStatus);
});

onBeforeUnmount(() => {
  window.removeEventListener("online", updateOnlineStatus);
  window.removeEventListener("offline", updateOnlineStatus);
});
</script>

<template>
  <header class="header">
    <h1>{{ online ? "PWA: ku, epta" : "PWA: ваша гравицапа сломалась" }}</h1>
    <div class="header__status">
      <div
        class="header__status-round"
        :class="online ? 'header__status--online' : 'header__status--offline'"></div>
      <span>{{ online ? "Online" : "Offline" }}</span>
    </div>
  </header>

  <div v-if="online">
    <Online :online="online" />
  </div>
  <div v-else>
    <Offline />
  </div>
</template>

<style lang="scss">
body {
  font-family: "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
}
</style>
