<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
    <div class="wrapper">
      <h1>Users App</h1>
      <RouterLink to="/">Home</RouterLink>
    </div>
  <RouterView />
</template>

<style scoped>
.wrapper{
  display: inline-block;
  margin-right: 1em;
}
</style>
