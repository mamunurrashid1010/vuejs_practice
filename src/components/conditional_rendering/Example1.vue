<template>
  <div>
    <h4>Conditional Rendering Example-1</h4>

    <!-- if-else   -->
    <p v-if="result" > Pass </p>
    <p v-else > Fail </p>

    <!-- if-else-if   -->
    <p v-if="marks >= 80">Marks : {{marks}}, Grade : A+</p>
    <p v-else-if="marks >= 60 && marks <80">Marks : {{marks}}, Grade : A</p>
    <p v-else-if="marks >= 40 && marks <60">Marks : {{marks}}, Grade : B</p>
    <p v-else>Fail, Marks : {{marks}}, Grade : F</p>

  </div>
</template>

<script>
export default {
  name:'Example1',
  data(){
    return{
      result:true,
      marks: 70,
    }
  },
  components:{

  },
  methods:{

  }
}
</script>

<style>

</style>