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
      loading: true,
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
          // this.loading = false;
          this.store.contenitoreGenerale = response.data.data.slice(0, 20);
        });
    },
  },
  created() {
    this.getCharacters();

    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php", {})
      .then((response) => {
        this.loading = false;
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
        <SearchForm @search="getCharacters()" />
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped></style>
