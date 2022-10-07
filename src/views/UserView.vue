<script setup>
  import { useRoute } from 'vue-router'
import { ref, watch } from 'vue'
import axios from 'axios'
import { User } from '../models/user'
import { onMounted } from 'vue'

  const route = useRoute()
  const userData = ref({})

  onMounted( () => {
    axios.get('https://jsonplaceholder.typicode.com/users/'+route.params.id).then(response=>(
      userData.value=response.data,
      console.log(userData.value)
    ))
  })

</script>
<template>
  <div>
    <!-- {{userData.name}} -->
    <h1>User Details Page</h1>
   <table>
    <tr>
      <td>Name </td>
      <td>{{userData.name}}</td>
    </tr>
    <tr>
      <td>Email </td>
      <td>{{userData.email}}</td>
    </tr>
    <tr>
      <td>Phone </td>
      <td>{{userData.phone}}</td>
    </tr>
    <tr>
      <td>Company </td>
      <td>{{userData.company?.name}}</td>
    </tr>
   </table>
  </div>
</template>