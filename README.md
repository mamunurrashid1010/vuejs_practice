# Vue.js Practice
 Vue.js is an open-source model–view–viewmodel front end JavaScript framework for building user interfaces and single-page applications. In this project here i practice vuejs core concept.

#### Topics Practice:  <hr>

##### 1. Vue app create
* Create a new vue app using vitejs.

##### 2. Components
* Create a vue component.
* Nested component.

##### 3. CSS Scoped

##### 4. Props
* Props example (Parent to child component data passing)

##### 5. Conditional Rendering
* v-if and v-else
* v-else-if
* v-show

##### 6. Loop
* v-for 

##### 7. Event Handling
* Click event example
* Keyup event example
* Keypress event example

##### 8. Lifecycle hook

##### 9. Axios installation

##### 10. <a href="https://github.com/mamunurrashid1010/vue-routing-implement"> Vue routing implement </a>

##### 11. Http Request
* Get request
* Post request
* Get details
* Delete

##### 12. Child to parent component data passing

##### 13. Bootstrap installation and use in a program

##### 14. Form
* Registration form
* Login

<hr>

## Basic Concept
##### 1. How to create a new vue app using vitejs?
Open terminal and run this command
```
npm create vite@latest  
```
Then add project name, then select vue, then javascript... <br>
After successfully create project then run command
```
npm install 
npm run dev
```

##### 2. Components
##### 2.1 How to create a vue component?
Create a vue file ``` Home.vue ``` in components directory and write code like-<br>
```
<template>
  <div>
    <h1>Home page</h1>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data(){
    return{

    }
  }
}
</script>

<style>

</style>
```
##### 2.2 Nested component
Create a vue file ``` Profile.vue ``` in components directory and write code like-<br>
```
<template>
  <div>
    <h1>Profile page</h1>
  </div>
</template>

<script>
export default {
  name:'Profile',
  data(){

  }
}
</script>

<style>

</style>
```
Now load ``` Profile.vue ``` in the ``` Home.vue ``` component
``` 
<template>
  <div>
    <h1>Home page</h1>
    <Profile/>
  </div>
</template>

<script>
import Profile from "./Profile.vue";
export default {
  name: 'Home',
  data(){
    return{

    }
  },
  components:{
    Profile
  }
}
</script>

<style>

</style>
```

##### 3. CSS Scoped
CSS ``` scoped ``` use for effect css style only specific component. <br>
Example
```
<template>
  <div>
    <h1>Profile page</h1>
  </div>
</template>

<script>
export default {
  name:'Profile',
  data(){

  }
}
</script>

<style scoped>
h1{
  color: red;
  font-family: "Roboto Thin";
}
</style>
```

##### 4. Props
##### 4.1 Props example (Parent to child component data passing)
=> Create vue file ``` ParentComponent.vue ``` ``` ChildComponent.vue ``` in components/props directory. <br>
=> open ``` ParentComponent.vue ``` file and write code like
```
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
```
=> open ``` ChildComponent.vue ``` file and write code like
```
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
```

##### 5. Conditional Rendering
##### 5.1 v-if, v-else, v-else-if and v-show  example
Create vue file ``` Example1.vue ```  in components/conditional_rendering directory, then open and write code like- <br>
```
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
    
    <!-- v-show   -->
    <p v-show="result" >
      condition is true
    </p>

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
```

##### 6. Loop
##### 6.1 v-for loop example
Create vue file ``` loopExample.vue ```  in components/loop directory, then open and write code like- <br>
```
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
```

##### 7. Event Handling
##### 7.1 Click event example
Create vue file ``` ClickEvent.vue ```  in components/event_handling directory, then open and write code like- <br>
```
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
```

##### 7.2 Keyup event example
Create vue file ``` KeyupEvent.vue ```  in components/event_handling directory, then open and write code like- <br>
```
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
```

##### 8. Lifecycle hook example
Create vue file ``` Example.vue ```  in components/lifecycle_hook directory, then open and write code like- <br>
```
<template>
  <div>
    <h4>Life cycle hook example</h4>
    <p>Name : {{name}}</p>
    <button @click="change()">change name</button>
  </div>
</template>

<script>
export default {
  name:'Example',
  data(){
    return{
        name:'Hasan',
    }
  },
  methods:{
    change(){
      this.name = "Mamunur Rashid";
    }
  },
  beforeCreate() {
    // code write here
    alert('beforeCreate hook');
  },
  created() {
    // code write here
    alert('created hook');
  },
  beforeUpdate() {
    alert('beforeUpdate hook');
  },
  updated() {

  }

}
</script>

<style>

</style>
```

##### 9. Axios Installation 
``` 
npm install axios --save
``` 

##### 11. Http Request
##### 11.1 Get request example
Create a vue file ``` GetRequest.vue ``` file in components/http_request directory and write code like-<br>
```
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
```

##### 11.2 Post request example
Create a vue file ``` PostRequest.vue ``` file in components/http_request directory and write code like-<br>
```
<template>
  <div>
    <h4>Http post request example</h4>

    <form @submit.prevent="store()">
      <label>Title:</label>
      <input type="text" v-model="form.title" name="title" /><br>
      <label>Body:</label>
      <input type="text" v-model="form.body" name="body" /><br>
      <button>Submit</button>
    </form>

  </div>
</template>

<script>
import axios from "axios";
export default {
  name:'PostRequest',
  data(){
    return{
      form:{
        title:'',
        body:'',
        userId: 1,

      },
    }
  },
  methods:{
    store(){
      axios.post('https://jsonplaceholder.typicode.com/posts',this.form)
          .then(req=>{
            alert('success');
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
```

##### 11.3 Get details example
Create a vue file ``` GetDetails.vue ``` file in components/http_request directory and write code like-<br>
```
<template>
  <div>
    <h4>Http get details example</h4>

    <button @click="getData()">Get Details</button>

      <p>
        ID :{{post.id}} <br>
        Title :{{post.title}}<br>
        Message :{{post.body}}<br>
      </p>

  </div>
</template>

<script>
import axios from "axios";
export default {
  name:'GetDetails',
  data(){
    return{
      post:{},
    }
  },
  methods:{
    getData(){
      axios.get('https://jsonplaceholder.typicode.com/posts/1')
          .then(req=>{
            this.post = req.data;
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
```

##### 11.4 Delete example
Create a vue file ``` DeleteExample.vue ``` file in components/http_request directory and write code like-<br>
```
<template>
  <div>
    <h4>Http delete example</h4>

    <p>
      ID :{{post.id}} <br>
      Title :{{post.title}}<br>
      Message :{{post.body}}<br>
      <button @click="deleteData(post.id)">Delete</button>
    </p>

  </div>
</template>

<script>
import axios from "axios";
export default {
  name:'DeleteExample',
  data(){
    return{
      post:{
        id:1,
        title:"test title",
        body:"test desc",

      },
    }
  },
  methods:{
    deleteData(id){
      axios.delete('https://jsonplaceholder.typicode.com/posts/'+id)
          .then(req=>{
            alert('success')
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
```

##### 12 Child to parent data passing
=> Create vue file ``` Parent.vue ``` and ``` Child.vue ``` file in components/child_to_parent_data_passing directory <br>

=> Open ``` Parent.vue ``` and write code like-<br>
```
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
```

=> Now Open ``` Child.vue ``` and write code like-<br>
```
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
```

##### 13 Bootstrap installation and use in a program
Bootstrap install command
```
npm install bootstrap@5.3.0
```
Open ```main.js``` and Import bootstrap.min.css file from node_modules like- import '../node_modules/bootstrap/dist/css/bootstrap.min.css';
then write code
```
import { createApp } from 'vue'
import './style.css'
import '../node_modules/bootstrap/dist/css/bootstrap.min.css';
import App from './App.vue'

createApp(App).mount('#app')
```

##### 14 Form
##### 14.1 Registration form example
=> Create a vue file ``` FormExample.vue ``` file in components/form directory and write code like-<br>
```
<template>
  <div>
    <h4>Registration Example</h4>

    <form @submit.prevent="store()">
      <div class="row">
          <div class="col-md-6">
            <label class="form-label">Name</label>
            <input type="text" v-model="form.name" class="form-control" >
          </div>
          <div class="col-md-6">
            <label class="form-label">Phone</label>
            <input type="text" v-model="form.phone" class="form-control" >
          </div>
          <div class="col-md-6">
            <label class="form-label">Email address</label>
            <input type="email" v-model="form.email" class="form-control">
          </div>
          <div class="col-md-6">
            <label class="form-label">Password</label>
            <input type="password" v-model="form.password" class="form-control">
          </div>
        <div class="col-md-12"><br>
          <button type="submit" class="btn btn-primary btn-block">Submit</button>
        </div>
      </div>
    </form>

  </div>
</template>

<script>
export default {
  name:'FormExample',
  data(){
    return{
        form:{
          name: '',
          phone: '',
          email: '',
          password:'',
        }
    }
  },
  methods:{
    store(){
      alert(
          "Name:" +this.form.name +
          "Phone:" +this.form.phone +
          "Email:" +this.form.email +
          "Password:" +this.form.password
      );
    }
  }
}
</script>

<style scoped>

</style>
```

##### 14.2 Login example
=> Create a vue file ``` Login.vue ``` file in components/form directory and write code like-<br>
```
<template>
  <div>
    <h4>Login page example</h4>

    <form @submit.prevent="login()">
      <div class="row">
        <div class="col-md-6">
          <label class="form-label">Email address</label>
          <input type="email" v-model="form.email" class="form-control">
        </div>
        <div class="col-md-6">
          <label class="form-label">Password</label>
          <input type="password" v-model="form.password" class="form-control">
        </div>
        <div class="col-md-12"><br>
          <button type="submit" class="btn btn-primary btn-block">Login</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name:'Login',
  data(){
    return{
      form:{
        email:'',
        password:''
      }
    }
  },
  methods:{
    login(){
      console.log(this.form)
      axios.post('api/login',this.form)
          .then(res=>{
            if(res.data===true)
              this.$router.push('/dashboard');
            else{
              alert('Fail!');
            }
          })
          .catch(e=>{

          })
    }
  }
}
</script>

<style scoped>

</style>
```