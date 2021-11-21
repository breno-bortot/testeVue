<template>
  <div class="container-fluid">
    <b-card border-variant="info" header="Filtros" align="start">
      <b-card-text
        ><div class="container-fluid d-flex flex-wrap" v-if="tableHead">
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
          /></div
      ></b-card-text>
    </b-card>
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