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
      <h1 class="py-5">Yu-Gi-Oh Api</h1>
    </div>
    <div class="bg-warning">
      <div class="container text-start py-3">
        <SearchForm />
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped></style>
