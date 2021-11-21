<template>
  <table
    v-if="operadoras"
    class="table table-bordered table-hover table-condensed"
  >
    <thead v-if="tableHead && tableHead.__parsed_extra">
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
        <th>{{ tableHead["Relação de Operadoras Ativas ANS"] }}</th>
      </tr>
    </thead>
    <tbody v-for="(data, i) in operadoras" :key="i">
      <tr>
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
        <td>{{ data["Relação de Operadoras Ativas ANS"] }}</td>
      </tr>
    </tbody>
  </table>
</template>
<script>
export default {
  name: "Table",
  props: {
    operadoras: Array,
    tableHead: Object,
  },
};
</script>
<style>
</style>