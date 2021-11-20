<template>
  <div class="container pt-3 pb-5">
    <h2></h2>

    <table class="table table-bordered table-hover table-condensed">
      <thead>
        <tr>
          <th>{{ tableHead.__parsed_extra[0] }}</th>
          <th>{{ tableHead.__parsed_extra[1] }}</th>
          <th>{{ tableHead.__parsed_extra[2] }}</th>
          <th>{{ tableHead.__parsed_extra[3] }}</th>
          <th>{{ tableHead.__parsed_extra[4] }}</th>
          <th>{{ tableHead.__parsed_extra[5] }}</th>
          <th>{{ tableHead.__parsed_extra[6] }}</th>
          <th>{{ tableHead.__parsed_extra[7] }}</th>
          <th>{{ tableHead.__parsed_extra[8] }}</th>
          <th>{{ tableHead.__parsed_extra[9] }}</th>
          <th>{{ tableHead.__parsed_extra[10] }}</th>
          <th>{{ tableHead.__parsed_extra[11] }}</th>
          <th>{{ tableHead.__parsed_extra[12] }}</th>
          <th>{{ tableHead.__parsed_extra[13] }}</th>
          <th>{{ tableHead.__parsed_extra[14] }}</th>
          <th>{{ tableHead.__parsed_extra[15] }}</th>
          <th>{{ tableHead.__parsed_extra[16] }}</th>
          <th>{{ tableHead.__parsed_extra[17] }}</th>
        </tr>
      </thead>
      <tbody v-for="(data, i) in operadoras" :key="i">
        <tr v-if="i !== 0">
          <td>{{ data.__parsed_extra[0] }}</td>
          <td>{{ data.__parsed_extra[1] }}</td>
          <td>{{ data.__parsed_extra[2] }}</td>
          <td>{{ data.__parsed_extra[3] }}</td>
          <td>{{ data.__parsed_extra[4] }}</td>
          <td>{{ data.__parsed_extra[5] }}</td>
          <td>{{ data.__parsed_extra[6] }}</td>
          <td>{{ data.__parsed_extra[7] }}</td>
          <td>{{ data.__parsed_extra[8] }}</td>
          <td>{{ data.__parsed_extra[9] }}</td>
          <td>{{ data.__parsed_extra[10] }}</td>
          <td>{{ data.__parsed_extra[11] }}</td>
          <td>{{ data.__parsed_extra[12] }}</td>
          <td>{{ data.__parsed_extra[13] }}</td>
          <td>{{ data.__parsed_extra[14] }}</td>
          <td>{{ data.__parsed_extra[15] }}</td>
          <td>{{ data.__parsed_extra[16] }}</td>
          <td>{{ data.__parsed_extra[17] }}</td>
        </tr>
      </tbody>
    </table>
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
    };
  },
  async created() {
    this.operadoras = await this.fetchOperadoras();
  },
  computed: {
    tableHead() {
      return this.operadoras[0];
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
