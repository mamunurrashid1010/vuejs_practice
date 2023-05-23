# Vue.js Practice
 Vue.js is an open-source model–view–viewmodel front end JavaScript framework for building user interfaces and single-page applications. In this project here i practice vuejs core concept.

#### Topics Practice:  <hr>

##### 1. Vue app create
* Create a new vue app using vitejs.

##### 2. Components
* Create a vue component.
* Nested component.
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