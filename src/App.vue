<script>
import AppMain from "./components/AppMain.vue";

export default {
  name: "App",
  components: {
    AppMain,
  },
};
</script>

<template>
  <main>
    <AppMain />
  </main>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "bootstrap/scss/bootstrap" as *;

body {
  background-color: #f5f7fa;
}
</style>
