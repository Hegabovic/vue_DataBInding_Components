<template>
  <div class="font-monospace fw-bold mb-2">Admin Users</div>
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
    <tr v-for="admin,index in admins" :key="index">
      <td>{{admin.username}}</td>
      <td>{{admin.age}}</td>
      <td>{{admin.address}}</td>
      <td>
        <button @click="$emit('deleteRecord',index)" class="btn btn-danger">delete</button>
      </td>
    </tr>
    </tbody>

  </table>
</template>

<script>
export default {
  name: "AdminComponent",
  props:['admins'],
  emits:['deleteRecord'],
  data(){
    return {

    }
  },
  methods: {


  }

}
</script>

<style scoped>

</style>