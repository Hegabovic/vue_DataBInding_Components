<template>
  <div class="font-monospace fw-bold mb-2">Student Users</div>
  <table class="table table-dark table-striped table-hover">
    <thead>
    <tr>
      <th>name</th>
      <th>age</th>
      <th>address</th>
      <th>options</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="student ,index in students" :key="student">
      <td>{{student.username}}</td>
      <td>{{student.age}}</td>
      <td>{{student.address}}</td>

      <td>
        <button @click="$emit('deleteRecordStudent',index)" class="btn btn-danger">delete</button>
      </td>
    </tr>
    </tbody>

  </table>
</template>
<script>
export default {
  name: "StudentComponent",
  props:['students'],
  emits:['deleteRecordStudent'],
  data() {
    return {
    }
  },
  methods: {

  }
}
</script>

<style scoped>

</style>