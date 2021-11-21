<template>
  <div class="container-fluid">
    <h3>Filtros</h3>
    <div class="container-fluid d-flex flex-wrap" v-if="tableHead">
      <SearchBar
        v-for="(data, i) in tableHead.__parsed_extra"
        :key="i"
        :index="i"
        :label="tableHead.__parsed_extra[i]"
        @search-submit="getSearchInput"
      />
      <SearchBar
        :label="tableHead['Relação de Operadoras Ativas ANS']"
        @search-submit="getSearchInput"
      />
    </div>
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
    getSearchInput(searchInput, index) {
      this.$emit("search-submit", searchInput, index);
    },
  },
};
</script>

<style>
</style>