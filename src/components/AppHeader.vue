<script>
import SearchForm from "./SearchForm.vue";

export default {
  name: "AppHeader",
  components: {
    SearchForm,
  },
};
</script>

<template>
  <header>
    <h1>Yu-Gi-Oh Api</h1>

    <SearchForm />
  </header>
</template>

<style lang="scss" scoped></style>
