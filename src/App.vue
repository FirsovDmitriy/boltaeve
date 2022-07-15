<template>
  <div class="wrapper">
    <TheHeader />
    <main class="main">
      <FullScreen />
    </main>
    <TheFooter />
  </div>
</template>

<script>
import TheFooter from "@/components/TheFooter.vue";
import TheHeader from "@/components/navigation/TheHeader.vue";
import FullScreen from "./components/fullscreen/FullScreen.vue";

export default {
  name: "App",
  components: { TheFooter, TheHeader, FullScreen },
};
</script>

<style lang="scss">
@import "./assets/index.scss";
</style>
