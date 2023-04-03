<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";
import AppLoader from "./components/AppLoader.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppLoader,
    AppMain,
    AppFooter,
  },
};
</script>

<template>
  <AppHeader />
  <AppMain />
  <AppFooter />
</template>

<style lang="scss">
@import "./styles/main.scss";
@import "./styles/loader.scss";
@import "./styles/CharacterrCard.scss";
</style>
