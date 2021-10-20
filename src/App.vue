<template>
  <Grid />
</template>

<script>
import Grid from "./components/Grid.vue";

export default {
  name: "App",
  components: {
    Grid,
  },
};
</script>

<style lang="scss">
@import "@/sass/main.scss";

#app {
  display: flex;
  justify-content: center;
  align-items: center;

  min-height: 100vh;
  min-width: 100vw;

  background-color: $COLOR_BG;
}
</style>
