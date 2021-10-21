<template>
  <div role="application">
    <Grid />
    <Attribution />
  </div>
</template>

<script>
import Grid from "./components/Grid.vue";
import Attribution from "./components/Attribution.vue";

export default {
  name: "App",
  components: {
    Grid,
    Attribution,
  },
};
</script>

<style lang="scss">
@import "@/sass/main.scss";

#app {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  min-width: 375px;
  min-height: 1966px;

  @include mq($from: desktop) {
    min-height: 100vh;
    min-width: 100vw;
  }

  background-color: $COLOR_BG;
}
</style>
