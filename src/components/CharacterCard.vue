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
        :src="character.card_images.image_url"
        alt="card image"
        class="img-fluid"
      />
    </div>
    <div class="bg-warning p-4">
      <h3>{{ character.name }}</h3>
      <h5>{{ character.archetype }}</h5>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
