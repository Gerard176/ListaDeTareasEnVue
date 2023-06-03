<script setup>
import { ref } from 'vue';
import Tarea from './components/Tarea.vue';
 const taskList = ref( [
  'Ver Shrek 2 por 15ava vez',
  'Ver la 17ava pelicula de rapidos y furiosos',
  'llorar por la muerte de Jonh Wick',

 ])
  let newTask 

 const deleteFromArray = (index)=>{
  console.log('kill',taskList)
  taskList.value.splice(index, 1)
 }
 const nuevaTarea = () =>{
  taskList.value.push(newTask)
 }
</script>

<template>
  <div class="px-4 py-3 mx-auto mt-12 space-y-2 overflow-hidden rounded shadow-md bg-gray-50 w-96" >
    <h1>Lista de tareas</h1>
    <div class="flex">
      <input  class="w-4/5 h-8 px-2 py-1 border border-r-0 border-e-red-500 rounded rounded-r-none " v-model="newTask"  type="text">
    <span class="w-1/5 h-8 text-xl font-bold text-center text-white bg-black border-1-0 rounded rounded-l-none leading-0 hover:bg-blue-700 hover:cursor-pointer "  @click="nuevaTarea" >
      +
    </span>   
    </div>

    <Tarea v-for="(task,index) in taskList" :key="index" :name="task" :index="index" @emitTarea="deleteFromArray"/>

  </div>

</template>

<style scoped>

</style>
