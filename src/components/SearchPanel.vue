<template>
  <div class="container">
    <SearchBar @search-submit="getSearchInput" />
  </div>
</template>

<script>
import SearchBar from "./subComponents/SearchBar.vue";
export default {
  name: "SearchPanel",
  components: {
    SearchBar,
  },
  emits: ["search-submit"],
  methods: {
    getSearchInput(searchInput) {
      this.$emit("search-submit", searchInput);
    },
  },
};
</script>

<style>
</style>