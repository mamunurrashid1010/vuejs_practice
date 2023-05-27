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