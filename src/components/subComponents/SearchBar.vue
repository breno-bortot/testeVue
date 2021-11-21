<template>
  <div class="container">
    <div class="form-group row">
      <label for="search" class="form-label mt-2 text-info">{{ label }} </label>
      <div class="input-group mb-1">
        <input
          @keyup.enter="$emit('search-submit', searchInput, index)"
          type="text"
          class="col-sm-8 form-control"
          id="search"
          v-model="searchInput"
          placeholder="Buscar aqui"
        />

        <button
          @click="$emit('search-submit', searchInput, index)"
          class="btn btn-info"
          type="button"
          id="button-addon2"
        >
          Buscar
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