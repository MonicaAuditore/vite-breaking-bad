<script>
import CharacterCard from "./CharacterCard.vue";

export default {
  name: "AppMain",
  props: {
    charactersList: {
      type: Array,
      default: [],
    },
    charachtersCount: {
      type: Number,
      default: 0,
    },
  },
  components: {
    CharacterCard,
  },
};
</script>

<template>
  <div class="bg-warning">
    <div class="container">
      <div class="bg-white p-5">
        <div class="text-start bg-black text-light py-3 ps-4">
          <strong>Found {{ charachtersCount }} cards</strong>
        </div>

        <main>
          <div
            class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5 g-4"
          >
            <div class="col text-center" v-for="character in charactersList">
              <CharacterCard :character="character" />
            </div>
          </div>
        </main>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
