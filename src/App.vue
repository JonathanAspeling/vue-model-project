<template>
<h1>{{title}}</h1>
<Model :header="header" :text="text" :theme="theme" />
</template>

<script>

import Model from './components/Model.vue';

export default {
  name: "App",
  components: {Model},
  data(){
    return{
      title:'My first Vue App :)',
      header:'Sign-up for the give away!',
      text:'Grab your ninja swag for half price',
      theme:'sale',
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }

  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
 border-bottom: 1px solid #ddd;
 display: inline-block;
 padding-bottom: 10px;
}
</style>
