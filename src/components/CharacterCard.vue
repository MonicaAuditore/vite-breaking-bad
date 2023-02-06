<script>
export default {
  name: "CharacterCard",
  props: {
    character: Object,
  },
};
</script>

<template>
  <div>
    <div v-if="loading">
      <h1>LOADING...</h1>
    </div>
    <div v-else>
      <div>
        <img
          :src="character.card_images[0].image_url"
          alt="card image"
          class="img-fluid"
        />
      </div>
      <div class="bg-warning p-4">
        <h3 class="text-white">{{ character.name }}</h3>
        <h5>{{ character.archetype }}</h5>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
