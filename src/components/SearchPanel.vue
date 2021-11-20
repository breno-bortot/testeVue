<template>
  <div class="container" v-if="tableHead">
    <SearchBar
      v-for="(data, i) in tableHead.__parsed_extra"
      :key="i"
      :label="tableHead.__parsed_extra[i]"
      @search-submit="getSearchInput"
    />

    <SearchBar
      :label="tableHead['Rela��o de Operadoras Ativas ANS']"
      @search-submit="getSearchInput"
    />
  </div>
</template>

<script>
import SearchBar from "./subComponents/SearchBar.vue";
export default {
  name: "SearchPanel",
  components: {
    SearchBar,
  },
  props: {
    tableHead: Object,
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