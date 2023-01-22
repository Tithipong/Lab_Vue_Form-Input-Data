<template>
  <table class="table" style="font-size: 9pt">
    <thead>
      <tr>
        <th>Date1</th>
        <th>Faculty1</th>
        <th>Name</th>
        <th>Student ID</th>
        <th>Telephone</th>
        <th>Network</th>
        <th>Course1</th>
        <th>Course2</th>
        <th>Major1</th>
        <th>Faculty2</th>
        <th>Major2</th>
        <th>Reason</th>
        <th>Date2</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(data, i) in formDataArray" v-bind:key="i">
        <td>{{ data.date1 }}</td>
        <td>{{ data.faculty1 }}</td>
        <td>{{ data.name }}</td>
        <td>{{ data.studentID }}</td>
        <td>{{ data.telephone }}</td>
        <td>{{ data.network }}</td>
        <td>{{ data.major1 }}</td>
        <td>{{ data.faculty2 }}</td>
        <td>{{ data.course1 }}</td>
        <td>{{ data.course2 }}</td>
        <td>{{ data.major2 }}</td>
        <td>{{ data.reason }}</td>
        <td>{{ data.date2 }}</td>
        <td>{{ data.email }}</td>
      </tr>
    </tbody>
  </table>
</template>
<script setup>
defineProps({
  formDataArray: Array,
});
</script>
<style scoped></style>
