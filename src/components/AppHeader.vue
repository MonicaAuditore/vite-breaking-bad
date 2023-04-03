<script>
import axios from "axios";
import { store } from "../store";
import SearchForm from "./SearchForm.vue";

export default {
  name: "AppHeader",
  components: {
    SearchForm,
  },
  data() {
    return {
      store,
    };
  },

  methods: {
    getCharacters() {
      console.log("sono in get characters");

      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php", {
          params: {
            archetype: this.store.archetiopoInput,
          },
        })
        .then((response) => {
          this.store.contenitoreGenerale = response.data.data.slice(0, 20);
        });
    },
    resetSearch() {},
  },
  created() {
    this.getCharacters();
    this.store.loading = true;
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php", {})
      .then((response) => {
        this.store.loading = false;
        this.store.contenitoreGenerale = response.data.data.slice(0, 20);
      });

    axios
      .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
      .then((response) => {
        this.store.nameValue = response.data;
      });
  },
};
</script>

<template>
  <header>
    <div class="container text-start">
      <h1 class="py-5">Yu-Gi-Oh Api</h1>
    </div>
    <div class="bg-warning">
      <div class="container text-start py-3">
        <SearchForm @search="getCharacters" @clear="resetSearch" />
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped></style>
