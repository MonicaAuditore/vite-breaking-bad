<script>
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
};
</script>

<template>
  <div class="bg-warning">
    <div class="container">
      <div class="bg-white p-5">
        <div class="text-start bg-black text-light py-3 ps-4">
          <strong>Found {{ charachtersCount }} cards</strong>
        </div>

        <main class="">
          <div
            class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5 g-4"
          >
            <div class="col text-center" v-for="charachters in charactersList">
              <div>
                <img
                  src="https://via.placeholder.com/300"
                  alt="card image"
                  class="img-fluid"
                />
              </div>
              <div class="bg-warning p-4">
                <h3>Character name</h3>
                <h5>Character status</h5>
              </div>
            </div>
          </div>
        </main>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
