
<script setup>
  import { ref } from 'vue';
  const todos = ref([{}]);
  
  function TodoInput(event){
    todos.value.push( {
      title:event.target.value,
      id: Math.floor(Math.random()*5000),
      completed:false,
    });
   console.log(todos); 
  }
</script>

<template>
  <input @keyup.enter="TodoInput"  placeholder="What needs to be done?">
  <ul>
    <li v-for="item of todos" :key="item.id">{{item.title}}</li>
  </ul>
</template>

<style>
.title {
  color: red;
}
</style>