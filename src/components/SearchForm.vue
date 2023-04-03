<script>
import { store } from "../store";
export default {
  name: "SearchForm",
  data() {
    return {
      store,
    };
  },
  methods: {
    formSottomesso() {
      console.log("form sottomesso");
    },
  },
};
</script>

<template>
  <div class="col-lg-2 my-5">
    <form action="" @submit.prevent="formSottomesso()">
      <select
        v-model="store.archetiopoInput"
        class="form-select"
        aria-label="Select category"
      >
        <option selected value="">Select archetype</option>
        <option
          v-for="archetipo in store.nameValue"
          :value="archetipo.archetype_name"
        >
          {{ archetipo.archetype_name }}
        </option>
      </select>
      <button
        type="submit"
        class="btn btn-light my-3"
        v-on:click="$emit('search')"
      >
        cerca
      </button>
      <!-- <button
        type="submit"
        class="btn btn-light my-3 mx-3"
        :click="$emit('clear')"
      >
        reset
      </button> -->
    </form>
  </div>
</template>

<style lang="scss" scoped></style>
