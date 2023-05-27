<template>
  <div>
    <h4>Child Component</h4>
    <p>Name: {{name}}</p>
    <p>
      <span v-for="data in testDetails">
        Designation: {{data.designation}},
        Experience: {{data.experience}}
        <br/>
      </span>
    </p>
  </div>
</template>

<script>
export default {
  name: 'ChildComponent',
  props:['name','testDetails'],
  data(){
    return{

    }
  },

}
</script>

<style>

</style>