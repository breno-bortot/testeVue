<template>
  <div class="container col-sm-12 col-md-6 col-lg-4">
    <div class="form-group row">
      <label for="search" class="form-label mt-4">{{ label }} </label>
      <div class="input-group mb-3">
        <input
          @keyup.enter="$emit('search-submit', searchInput, index)"
          type="text"
          class="col-sm-8 form-control"
          id="search"
          v-model="searchInput"
          placeholder="search here"
        />

        <button
          @click="$emit('search-submit', searchInput, index)"
          class="btn btn-primary"
          type="button"
          id="button-addon2"
        >
          Search
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "SearchBar",
  data() {
    return {
      searchInput: "",
    };
  },
  props: {
    label: String,
    index: Number,
  },
};
</script>
<style>
</style>