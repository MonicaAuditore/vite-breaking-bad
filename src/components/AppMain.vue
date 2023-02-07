<script>
import CharacterCard from "./CharacterCard.vue";
import { store } from "../store";
export default {
  name: "AppMain",
  components: {
    CharacterCard,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="bg-warning">
    <div class="container">
      <div class="bg-white p-5">
        <div class="text-start bg-black text-light py-3 ps-4">
          <strong>Found {{ store.contenitoreGenerale.length }} cards</strong>
        </div>

        <main>
          <div
            class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5 g-4"
          >
            <div
              class="col text-center"
              v-for="character in store.contenitoreGenerale"
            >
              <CharacterCard :character="character" />
            </div>
          </div>
        </main>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
