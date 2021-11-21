<template>
  <div class="container pt-3 pb-5">
    <h2>Lista de cadastro de operadoras</h2>
    <SearchPanel :tableHead="tableHead" @search-submit="filterAction" />
    <Table :tableHead="tableHead" :operadoras="filteredOperadoras" />
  </div>
</template>

<script>
import papa from "papaparse";
import Table from "./components/Table.vue";
import SearchPanel from "./components/SearchPanel.vue";

export default {
  name: "App",
  components: {
    Table,
    SearchPanel,
  },
  data() {
    return {
      tableBody: [],
      tableHead: [],
      searchInput: "",
    };
  },
  async created() {
    const table = await this.fetchOperadoras();
    const tableHead = table.shift();
    const tableBody = table;

    this.tableHead = tableHead;
    this.tableBody = tableBody;
  },
  computed: {
    filteredOperadoras() {
      return this.tableBody.filter((operadora) =>
        operadora.__parsed_extra[1]
          .toLowerCase()
          .match(this.searchInput.toLowerCase())
      );
    },
  },

  methods: {
    async fetchOperadoras() {
      const result = await fetch("dados/Relatorio_cadop.csv");
      const data = await result.text();
      const csvToJson = papa.parse(data, {
        header: true,
        dynamicTyping: true,
        skipEmptyLines: true,
        complete(result) {
          return result.data;
        },
      });
      // console.log(csvToJson.data);
      return csvToJson.data;
    },
    filterAction(searchInput) {
      this.searchInput = searchInput;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
