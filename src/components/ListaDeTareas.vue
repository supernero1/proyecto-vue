<template>
    <div>
        <h2>Lista de Tareas</h2>
        <input type="text" v-model="newtarea" @keyup.enter="addtarea">
        <ul>
            <li v-for="(tarea, index) in tareas" :key="index">
                {{ tarea }}
                <button @click="borrarTarea">Delete</button>
            </li>
        </ul>
    </div>
</template>
<script setup>
import {ref} from 'vue';
const tareas = ref([]);
const newtarea = ref(' ');
const addtarea = () => {
    tareas.value.push(newtarea.value);
    newtarea.value = ''; 
}
const borrarTarea = (index)=> {
    tareas.value.splice(index,1)
}

</script>
<style>
    
</style>