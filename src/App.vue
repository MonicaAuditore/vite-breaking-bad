<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
};
</script>

<template>
  <AppHeader />
  <div class="text-center">
    <div v-if="loading"><span class="loader"></span></div>
    <div v-else>
      <AppMain />
    </div>
  </div>

  <AppFooter />
</template>

<style lang="scss">
@import "./styles/main.scss";
@import "./styles/loader.scss";
</style>
