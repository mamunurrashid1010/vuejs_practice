<template>
  <div>
    <!--  example-1 -->
    <h4>Mouse over example</h4>
    <button class="btn btn-warning" @mousemove="show()">Mouseover</button>

  </div>
</template>

<script>
export default {
  name:'Mouseover',
  data(){
    return{

    }
  },
  methods:{
    show(){
      alert("test");
    }
  }
}
</script>

<style>

</style>