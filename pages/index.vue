<template>
    <div class="max-w-md mx-auto mt-10 p-4 shadow-md">
      <h2 class="text-2xl font-semibold mb-4 text-center text-red-500">My To-Do List</h2>
  
      <div class="mb-4">
        <input v-model="newTodo" type="text" class="w-full p-2 mt-10 border rounded-lg"/>
        
        <button @click="addTodo" class="w-full mt-10 p-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">
          Add new task
        </button>
        
      </div>
  
      <ul>
        <li v-for="(todo, index) in todos" :key="index" class="flex justify-between items-center mb-2">
          <span :class="{'text-gray-400': todo.completed}" class="text-lg">
            {{ todo.text }}
          </span>
          
          <button @click="toggleComplete(index)" class="ml-2 text-green-500 hover:text-green-700" v-if="!todo.completed">
            Completed
          </button>
          
          <button @click="removeTodo(index)" class="ml-2 text-red-500 hover:text-red-700">
            Remove
          </button>
        </li>
      </ul>
  
      <p v-if="todos.length === 0" class="text-center text-gray-500 mt-4">
        No task!
      </p>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  

  const newTodo = ref('')
  const todos = ref([])
  
  
  const addTodo = () => {
    if (newTodo.value.trim()) {
      todos.value.push({ text: newTodo.value.trim(), completed: false })
      newTodo.value = ''  // Clear input field
    }
  }
  
 
  const toggleComplete = (index) => {
    todos.value[index].completed = !todos.value[index].completed
  }
  
 
  const removeTodo = (index) => {
    todos.value.splice(index, 1)
  }
  </script>
  
  <style scoped>
  
  </style>
  