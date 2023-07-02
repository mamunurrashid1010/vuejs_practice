<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Profile from "./components/Profile.vue";
import Home from "./components/Home.vue";
import ParentComponent from "./components/props/ParentComponent.vue";
import Example1 from "./components/conditional_rendering/Example1.vue";
import LoopExample from "./components/loop/loopExample.vue";
import ClickEvent from "./components/event_handling/ClickEvent.vue";
import Example from "./components/lifecycle_hook/Example.vue";
import GetRequest from "./components/http_request/GetRequest.vue";
import PostRequest from "./components/http_request/PostRequest.vue";
import GetDetails from "./components/http_request/GetDetails.vue";
import DeleteExample from "./components/http_request/DeleteExample.vue";
import Parent from "./components/child_to_parent_data_passsing/Parent.vue";
import FormExample from "./components/form/FormExample.vue";
import Login from "./components/form/Login.vue";
import KeyupEvent from "./components/event_handling/KeyupEvent.vue";
import Keypress from "./components/event_handling/Keypress.vue";
import CtrlClick from "./components/event_handling/CtrlClick.vue";
import Mouseover from "./components/event_handling/Mouseover.vue";
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <Home/>

  <!-- props example -->
  <h3 style="color: green">Props Example</h3><hr>
  <ParentComponent/>

  <!-- conditional Rendering example -->
  <h3 style="color: green">Conditional Rendering Example</h3><hr>
  <Example1/>

  <!-- loop example -->
  <h3 style="color: green">Loop Example</h3><hr>
  <loop-example/>

  <!-- event handling: click event example -->
  <h3 style="color: green">Event Handling</h3><hr>
  <ClickEvent/>
  <KeyupEvent/>
  <Keypress/>
  <CtrlClick/>
  <Mouseover/>

  <!-- lifecycle hook example -->
  <h3 style="color: green">Life cycle hook</h3><hr>
  <!--  <Example/>-->

  <!-- http request example -->
  <h3 style="color: green">Http request</h3><hr>
  <GetRequest/>
  <PostRequest/>
  <GetDetails/>
  <DeleteExample/>

  <!-- child to parent data passing example -->
  <h3 style="color: green">child to parent data passing</h3><hr>
  <Parent/>

  <!-- form example -->
  <h3 style="color: green">form example</h3><hr>
  <FormExample/>
  <Login/>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
