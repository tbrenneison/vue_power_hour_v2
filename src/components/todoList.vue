<template>
    <h1>{{store.currentCat.name}}'s To-Do List</h1>

    <ul>
        <li v-for="todo in store.todos" v-bind:key="todo.id"
            v-bind:class="{completed: todo.isComplete}">
            <input type="checkbox" v-model="todo.isComplete">
            {{ todo.item }}
        </li>
    </ul>

    <p>Todos Completed: {{  store.todosComplete }}</p>
    <p>Todos Left: {{ store.todosIncomplete }}</p>

    <todo-form/>


</template>

<script setup>
import TodoForm from '@/components/todoForm.vue'
import { useTodoStore } from '@/stores/todo.js'

const store = useTodoStore(); 

</script>

<style>
    li { 
        list-style-type: none;
    }
    
    .completed { 
        color: hotpink;
    }
</style>