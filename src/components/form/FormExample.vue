<template>
  <div>
    <h4>Registration Example</h4>

    <form @submit.prevent="store()">
      <div class="row">
          <div class="col-md-6">
            <label class="form-label">Name</label>
            <input type="text" v-model="form.name" class="form-control" >
          </div>
          <div class="col-md-6">
            <label class="form-label">Phone</label>
            <input type="text" v-model="form.phone" class="form-control" >
          </div>
          <div class="col-md-6">
            <label class="form-label">Email address</label>
            <input type="email" v-model="form.email" class="form-control">
          </div>
          <div class="col-md-6">
            <label class="form-label">Password</label>
            <input type="password" v-model="form.password" class="form-control">
          </div>
        <div class="col-md-12"><br>
          <button type="submit" class="btn btn-primary btn-block">Submit</button>
        </div>
      </div>
    </form>

  </div>
</template>

<script>
export default {
  name:'FormExample',
  data(){
    return{
        form:{
          name: '',
          phone: '',
          email: '',
          password:'',
        }
    }
  },
  methods:{
    store(){
      alert(
          "Name:" +this.form.name +
          "Phone:" +this.form.phone +
          "Email:" +this.form.email +
          "Password:" +this.form.password
      );
    }
  }
}
</script>

<style scoped>

</style>