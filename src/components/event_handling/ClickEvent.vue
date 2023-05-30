<template>
  <div>
    <!--  example-1 -->
    <h4>Click event example-1</h4>
    <p>Counter value : {{count}}</p>
    <button @click="count++">+</button>
    <button @click="count--">-</button>

    <!--  example-2 -->
    <h4>Click event example-2</h4>
    <button @click="show()">Click me</button>

  </div>
</template>
<script>
export default {
  name:'ClickEvent',
  data(){
    return{
      count:0,
    }
  },
  methods:{
    show(){
      alert("counter value is :"+this.count);
    }
  }
}
</script>
<style>
button{
  background-color: #747bff;
  margin-right: 5px;
}
</style>