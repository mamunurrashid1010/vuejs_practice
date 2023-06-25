<template>
  <div>

    <h4>Keypress example</h4>
    <p>Name : {{title}}</p>
    <input type="text" name="" value="" @keypress="nameChange()" />

  </div>
</template>

<script>
export default {
  name:'Keypress',
  data(){
    return{
      title:''
    }
  },
  methods:{
    nameChange(e){
      this.title = e.target.value;
    }
  }
}
</script>

<style>

</style>