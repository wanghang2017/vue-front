<template>
  <div id="app">
    <ul>
      <li v-for="(user) in users" :key="user.id">
        <span>{{user.name}}</span>
      </li>
    </ul>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import axios from "axios";
export default {
  name: 'app',
  data(){
    return{
      users:[]
    } 
  },
  mounted(){
    axios.get("http://localhost:3000/api/v1/users").then(res=>{
      this.users= res.data;
    })
  },
  
}
</script>

<style>

</style>
