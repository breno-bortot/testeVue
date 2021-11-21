<template>
  <div class="container-fluid mb-5">
    <b-card border-variant="info" header="Filtros" align="start">
      <div>
        <b-tabs content-class="mt-3" justified>
          <b-tab
            v-for="(data, i) in tableHead.__parsed_extra"
            :key="i"
            :title="tableHead.__parsed_extra[i]"
            active
          >
            <SearchBar
              :index="i"
              :label="tableHead.__parsed_extra[i]"
              @search-submit="getSearchInput"
          /></b-tab>
          <b-tab :title="tableHead['Relação de Operadoras Ativas ANS']" active>
            <SearchBar
              :label="tableHead['Relação de Operadoras Ativas ANS']"
              @search-submit="getSearchInput"
          /></b-tab>
        </b-tabs>
      </div>
      <b-card-text>
        <!-- <div class="container-fluid d-flex flex-wrap" v-if="tableHead">
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
        </div> -->
      </b-card-text>
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