<template>
  <div>
    <h4>Parent Component</h4>
    <p>Title: {{title}}</p>
    <Child @changeTitle="ChangeT($event)" />
  </div>
</template>

<script>
import Child from "./Child.vue";
export default {
  name:'Parent',
  data(){
    return{
        title:'',
    }
  },
  methods:{
    ChangeT(title){
      this.title=title;
    }
  },
  components:{
    Child
  }
}
</script>

<style scoped>

</style>