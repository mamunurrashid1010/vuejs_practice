<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Profile from "./components/Profile.vue";
import Home from "./components/Home.vue";
import ParentComponent from "./components/props/ParentComponent.vue";
import Example1 from "./components/conditional_rendering/Example1.vue";
import LoopExample from "./components/loop/loopExample.vue";
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
