<template>
    <h1>Zenith's To-Do List</h1>

    <ul>
        <li v-for="todo in todos" v-bind:key="todo.id"
            v-bind:class="{completed: todo.isComplete}">
            <input type="checkbox" v-model="todo.isComplete">
            {{ todo.item }}
        </li>
    </ul>

    <p>Todos Completed: {{  todosComplete }}</p>
    <p>Todos Left: {{ todosIncomplete }}</p>

    <todoForm @addTodo="addTodo"/>
    <!-- <form v-on:submit.prevent="addTodo">
        Item: 
        <input type="text" v-model="newTodo.item">
        <br>
        Complete? 
        <input type="checkbox" v-model="newTodo.isComplete"> 
        <br>
        <input type="submit" value="Add To-do">
    </form> -->

</template>

<script setup>
import { ref, reactive, computed } from 'vue'
import todoForm from '@/components/todoForm.vue'

const todos = reactive([
                {
                    id: 1,
                    item: "Put my dirty litterbox paw in Momther's food", 
                    isComplete: false
                },
                {
                    id: 2,
                    item: "Roll around on Father's black pants", 
                    isComplete: false
                },
                {
                    id: 3,
                    item: "Trigger the Litter Robot to cycle for no reason", 
                    isComplete: false
                },
                {
                    id: 4,
                    item: "Open all the closet doors and have a look", 
                    isComplete: false
                }
])

// const newTodo = reactive({}) //moved to todoForm.vue
const currentTodoId = ref(5) 

const todosComplete = computed(() => {
    return todos.filter((todo) => {
                return todo.isComplete
            }).length;
}) 

const todosIncomplete = computed(() => {
    return todos.filter((todo) => {
                return !todo.isComplete
            }).length;
}) 

function addTodo(newTodo) { 
    let add = {...newTodo}
    add.id = currentTodoId;
    todos.push(add);
    newTodo.id = undefined; 
    newTodo.item = ''; 
    newTodo.isComplete = false;
    currentTodoId.value++;

}

</script>

<style>
    li { 
        list-style-type: none;
    }
    
    .completed { 
        color: hotpink;
    }
</style>