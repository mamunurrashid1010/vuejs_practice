<template>
  <div>
    <h4>Http get request example</h4>

    <button @click="getData()">Get</button>

    <div v-for="post in posts">
        <p v-if="post.id <=10">
            ID :{{post.id}} <br>
            Title :{{post.title}}<br>
            Message :{{post.body}}<br>
        </p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name:'GetRequest',
  data(){
    return{
        posts:[],
    }
  },
  methods:{
    getData(){
      axios.get('https://jsonplaceholder.typicode.com/posts')
          .then(req=>{
            this.posts = req.data;
          })
          .catch(e=>{
            alert('Error')
          })
    }
  }
}
</script>

<style scoped>

</style>