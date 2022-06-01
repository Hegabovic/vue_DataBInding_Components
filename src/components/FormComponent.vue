<template>

    <div class="mb-3">
      <label for="exampleInputEmail1" class="form-label">Name</label>
      <input type="text" class="form-control" id="exampleInputEmail1" v-model="formValues.username"
             aria-describedby="emailHelp" placeholder="User Name">
    </div>
    <div class="mb-3">
      <label for="InputAge" class="form-label">Age</label>
      <input type="text" class="form-control" id="InputAge" v-model="formValues.age" placeholder="Age">
    </div>
    <div class="mb-3">
      <label class="form-check-label" for="address">Email Address</label>
      <input type="email" class="form-control" id="address" v-model="formValues.address" placeholder="email address">
    </div>

    <div class="mb-3">
      <select name="roles" v-model="formValues.role" class="form-control">
        <option value="Student">Student</option>
        <option value="Admin">Admin</option>
      </select>


    </div>
    <button type="submit" @click="$emit('sendAdmins',formValues)" class="btn btn-dark">Submit</button>

</template>

<script>
export default {
  name: "FormComponent",
  emits:['sendAdmins'],
  data() {
    return {
      formValues: {
        username: '',
        age: '',
        address: '',
        role: '',
      },
    }
  },
  methods: {


  }
}
</script>

<style scoped>

</style>