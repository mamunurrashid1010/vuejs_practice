<template>
  <div>
    <h1>Home page</h1>
    <Profile/>
  </div>
</template>

<script>
import Profile from "./Profile.vue";
export default {
  name: 'Home',
  data(){
    return{

    }
  },
  components:{
    Profile
  }
}
</script>

<style>

</style>