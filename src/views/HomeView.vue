<template>
  <select v-model="store.currentCatId">
    <option v-for="cat in store.cats" v-bind:key="cat.id" v-bind:value="cat.id">
      {{ cat.name }}
    </option>
  </select>
  <todo-list/>
</template>

<script setup>
import TodoList from '@/components/todoList.vue'
import {useTodoStore} from '@/stores/todo.js'

const store = useTodoStore();
</script>

<style>

</style>
