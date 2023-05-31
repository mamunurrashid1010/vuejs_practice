<template>
  <div>
    <h4>Life cycle hook example</h4>
    <p>Name : {{name}}</p>
    <button @click="change()">change name</button>
  </div>
</template>

<script>
export default {
  name:'Example',
  data(){
    return{
        name:'Hasan',
    }
  },
  methods:{
    change(){
      this.name = "Mamunur Rashid";
    }
  },
  beforeCreate() {
    // code write here
    alert('beforeCreate hook');
  },
  created() {
    // code write here
    alert('created hook');
  },
  beforeUpdate() {
    alert('beforeUpdate hook');
  },
  updated() {

  }

}
</script>

<style>

</style>