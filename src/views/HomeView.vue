<script setup>
  import axios from 'axios'
  import {ref} from 'vue'
import { User } from '../models/user';

   const users = ref([])
  
    axios.get('https://jsonplaceholder.typicode.com/users').then(
      response =>(
        users.value=response.data
      ))
    
  
</script>

<template>
  
    <div>
      <ul>
      <li v-for="(user,index) in users" v-bind:key="user.id" >
        <RouterLink :to="'/users/' + user.id">{{index+1}}.{{user.name}}</RouterLink>
      </li>
      </ul>
    </div>
  
</template>
<style scoped>
ul{
  list-style-type: none;
}
</style>