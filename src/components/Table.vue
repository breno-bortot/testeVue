<template>
  <table class="table table-bordered table-hover table-condensed">
    <thead v-if="operadoras[0]">
      <tr>
        <th>{{ operadoras[0]["Rela��o de Operadoras Ativas ANS"] }}</th>
        <th>{{ operadoras[0].__parsed_extra[0] }}</th>
        <th>{{ operadoras[0].__parsed_extra[1] }}</th>
        <th>{{ operadoras[0].__parsed_extra[2] }}</th>
        <th>{{ operadoras[0].__parsed_extra[3] }}</th>
        <th>{{ operadoras[0].__parsed_extra[4] }}</th>
        <th>{{ operadoras[0].__parsed_extra[5] }}</th>
        <th>{{ operadoras[0].__parsed_extra[6] }}</th>
        <th>{{ operadoras[0].__parsed_extra[7] }}</th>
        <th>{{ operadoras[0].__parsed_extra[8] }}</th>
        <th>{{ operadoras[0].__parsed_extra[9] }}</th>
        <th>{{ operadoras[0].__parsed_extra[10] }}</th>
        <th>{{ operadoras[0].__parsed_extra[11] }}</th>
        <th>{{ operadoras[0].__parsed_extra[12] }}</th>
        <th>{{ operadoras[0].__parsed_extra[13] }}</th>
        <th>{{ operadoras[0].__parsed_extra[14] }}</th>
        <th>{{ operadoras[0].__parsed_extra[15] }}</th>
        <th>{{ operadoras[0].__parsed_extra[16] }}</th>
        <th>{{ operadoras[0].__parsed_extra[17] }}</th>
      </tr>
    </thead>
    <tbody v-for="(data, i) in operadoras" :key="i">
      <tr v-if="i !== 0">
        <td>{{ data["Rela��o de Operadoras Ativas ANS"] }}</td>
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
</template>
<script>
export default {
  name: "Table",
  props: {
    operadoras: Array,
    // tableHead: Object,
  },
};
</script>
<style lang="">
</style>