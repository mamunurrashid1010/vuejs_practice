<template>
  <div>
      <h4>Parent Component</h4>
      <ChildComponent name="Mamunur Rashid" :testDetails="details" />
  </div>
</template>

<script>
import ChildComponent from "./ChildComponent.vue";

export default {
  name: 'ParentComponent',
  data(){
    return{
        details:[
          {'designation':'Software developer', 'experience': '4years'},
          {'designation':'Rest API developer', 'experience': '2years'},
          {'designation':'Web Designer', 'experience': '2years'}
        ],
    }
  },
  components:{
    ChildComponent,
  }
}
</script>

<style>

</style>