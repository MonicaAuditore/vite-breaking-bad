<script>
import { store } from "../store";
export default {
  name: "SearchForm",
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="col-lg-2 my-5">
    <select
      v-model="store.statusValue"
      name="status"
      class="form-select"
      aria-label="Select category"
    >
      <option selected value="">Select category</option>
      <option v-for="archetipo in store.nameValue" value="1">
        {{ archetipo.archetype_name }}
      </option>
    </select>
    <button
      type="button"
      class="btn btn-light my-3"
      v-on:click="$emit('search')"
    >
      cerca
    </button>
  </div>
</template>

<style lang="scss" scoped></style>
