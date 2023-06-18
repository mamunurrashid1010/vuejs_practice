<template>
  <div>
    <h4>Chile Component</h4>
    <button type="button" @click='passEvent'> Update me</button>
  </div>
</template>

<script>
export default {
  name:'Child',
  data(){
    return{
      title:'',
    }
  },
  methods:{
    passEvent(){
      this.$emit('changeTitle','I am from child component');
    }
  },
  components:{

  }
}
</script>

<style scoped>

</style>