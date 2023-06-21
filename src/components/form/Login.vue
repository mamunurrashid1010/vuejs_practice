<template>
  <div>
    <h4>Login page example</h4>

    <form @submit.prevent="login()">
      <div class="row">
        <div class="col-md-6">
          <label class="form-label">Email address</label>
          <input type="email" v-model="form.email" class="form-control">
        </div>
        <div class="col-md-6">
          <label class="form-label">Password</label>
          <input type="password" v-model="form.password" class="form-control">
        </div>
        <div class="col-md-12"><br>
          <button type="submit" class="btn btn-primary btn-block">Login</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name:'Login',
  data(){
    return{
      form:{
        email:'',
        password:''
      }
    }
  },
  methods:{
    login(){
      console.log(this.form)
      axios.post('api/login',this.form)
          .then(res=>{
            if(res.data===true)
              this.$router.push('/dashboard');
            else{
              alert('Fail!');
            }
          })
          .catch(e=>{

          })
    }
  }
}
</script>

<style scoped>

</style>