<template>
  <div class="container pt-3 pb-5">
    <h2>Lista de cadastro de operadoras</h2>
    <SearchPanel />
    <Table :operadoras="operadoras" />
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
      operadoras: [],
    };
  },
  async created() {
    this.operadoras = await this.fetchOperadoras();
  },
  computed: {},
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
