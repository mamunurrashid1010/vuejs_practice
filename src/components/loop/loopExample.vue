<template>
  <div>
    <h4>v-for loop example-1</h4>
    <ul v-for="(data,index) in datas" :key="data.id">
      <li>
        Index : {{index}}
        ID    : {{data.id}}
        Title : {{data.title}}
      </li>
    </ul>

  </div>
</template>

<script>
export default{
  name:'loopExample',
  data(){
    return{
        datas:[
          {'id':1, title:'test1'},
          {'id':2, title:'test2'},
          {'id':3, title:'test3'},
          {'id':4, title:'test4'},
          {'id':5, title:'test5'}
        ],
    }
  },

}
</script>

<style>

</style>