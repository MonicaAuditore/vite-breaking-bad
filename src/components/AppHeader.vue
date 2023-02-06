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
    <div class="container text-start">
      <h1>Yu-Gi-Oh Api</h1>
      <SearchForm />
    </div>
  </header>
</template>

<style lang="scss" scoped></style>
