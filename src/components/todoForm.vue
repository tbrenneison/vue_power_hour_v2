<template>
    <form v-on:submit.prevent="store.addTodo">
          Item: 
          <input type="text" v-model="store.newTodo.item">
          <br>
          Complete? 
          <input type="checkbox" v-model="store.newTodo.isComplete"> 
          <br>
          <input type="submit" value="Add To-do">
      </form>
  </template>
  
  <script setup>
  import { reactive } from 'vue'
  import { useTodoStore } from '@/stores/todo';
//   const newTodo = reactive({})
const store = useTodoStore(); 
  
  </script>
  
  <style>
  
  </style>