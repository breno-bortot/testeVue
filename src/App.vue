<template>
  <div class="container pt-3 pb-5">
    <h2></h2>

    <b-table striped hover :operadoras="operadoras"></b-table>
  </div>
</template>

<script>
import papa from "papaparse";
export default {
  name: "App",
  components: {},
  data() {
    return {
      operadoras: [],
      items: [
        { age: 40, first_name: "Dickerson", last_name: "Macdonald" },
        { age: 21, first_name: "Larsen", last_name: "Shaw" },
        { age: 89, first_name: "Geneva", last_name: "Wilson" },
        { age: 38, first_name: "Jami", last_name: "Carney" },
      ],
    };
  },
  async created() {
    this.operadoras = await this.fetchOperadoras();
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
