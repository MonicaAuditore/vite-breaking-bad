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
    <div>
      <img
        :src="character.card_images[0].image_url"
        alt="card image"
        class="img-fluid"
      />
    </div>
    <div id="cardContainer" class="bg-warning p-4">
      <h4 class="text-white">{{ character.name }}</h4>
      <h6>{{ character.archetype }}</h6>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
