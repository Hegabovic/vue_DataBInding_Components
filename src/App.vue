<template>

  <div class="container">
    <img alt="Vue logo" src="./assets/logo.png">
    <div class="row d-flex justify-content-around mb-5">
      <div class="col-3">
        <button @click="formClick('student')" class="btn btn-dark">Student</button>
      </div>
      <div class="col-3">
        <button @click="formClick('admin')" class="btn btn-dark">Admin</button>
      </div>
      <div class="col-3">
        <button @click="formClick('form')" class="btn btn-dark">Form</button>
      </div>
    </div>
  </div>


  <div v-if="showStudent">
    <StudentComponent :students="this.students" @deleteRecordStudent="deleteRecordStudent"/>
  </div>
  <div v-else-if="showAdmin">
    <AdminComponent :admins="this.admins" @deleteRecord="deleteRecordAdmin"/>
  </div>
  <div v-else-if="showForm">
    <FormComponent @sendAdmins='save' />
  </div>


</template>

<script>
import StudentComponent from "@/components/StudentComponent";
import AdminComponent from "@/components/AdminComponent";
import FormComponent from "@/components/FormComponent";

export default {
  name: 'App',
  components: {
    StudentComponent,
    AdminComponent,
    FormComponent,
  },
  data() {
    return {
      showStudent: false,
      showAdmin: false,
      showForm: false,
      students:[],
      admins:[],
    }
  },

  methods: {
    formClick(type) {
      if (type === 'form') {
        this.showForm = true;
        this.showAdmin = false;
        this.showStudent = false;
      } else if(type === 'student'){
        this.showForm = false;
        this.showAdmin = false;
        this.showStudent = true;
      }else if(type === 'admin'){
        this.showForm = false;
        this.showAdmin = true;
        this.showStudent = false;
      }
    },
    save(data) {
      console.log(data)
      if(data.role ==='Student'){
        this.students.push(data)
      }else{
        this.admins.push(data)
      }
    },
    deleteRecordAdmin(index) {
      this.admins.splice(index, 1);
    },
    deleteRecordStudent(index) {
      this.students.splice(index, 1);
    }
  }
}
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
