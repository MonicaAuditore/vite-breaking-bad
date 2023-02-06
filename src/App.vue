<script>
import axios from "axios";
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

  data() {
    return {
      loading: true,
      charachters: [],
    };
  },
  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php")
      .then((response) => {
        this.loading = false;
        console.log(response.data.data.slice(0, 20));
        this.charachters = response.data.data.slice(0, 20);
      });
  },
};
</script>

<template>
  <AppHeader />
  <div class="text-center">
    <div v-if="loading"><span class="loader"></span></div>
    <div v-else>
      <AppMain
        :charactersList="charachters"
        :charachtersCount="charachters.length"
      />
    </div>
  </div>

  <AppFooter />
</template>

<style lang="scss">
@import "./styles/main.scss";
@import "./styles/loader.scss";
</style>
