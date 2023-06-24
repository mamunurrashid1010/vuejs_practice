<template>
  <div>

    <h4>Keyup event example</h4>
    <p>Name : {{title}}</p>
    <input type="text" name="" value="" @keyup="nameChange()" />

  </div>
</template>

<script>
export default {
  name:'KeyupEvent',
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