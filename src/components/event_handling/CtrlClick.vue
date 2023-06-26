<template>
  <div>

    <h4>Ctrl+Click event example</h4>
    <button class="btn btn-info" @click.ctrl="submit()">Ctrl+click</button>

  </div>
</template>

<script>
export default {
  name:'CtrlClick',
  data(){
    return{
    }
  },
  methods:{
    submit(){
      alert('Hello');
    }
  }
}
</script>

<style>

</style>