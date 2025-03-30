<script setup>
import { reactive, ref } from 'vue';

const todoData = reactive({
    name: '',
    email: '',
    phone: '',
    website: ''
})

const handleCreateNewData = async() => {
    console.log(todoData)
}
</script>

<template>
  <main class="container">
    <h2 style="margin-top: 1rem; font-weight: bold;">Create New</h2>
    <input class="input-data" type="text" placeholder="Enter Name Here" v-model="todoData.name"/>
    <input class="input-data"type="text" placeholder="Enter Email Here" v-model="todoData.email"/>
    <input class="input-data"type="text" placeholder="Enter Phone Here" v-model="todoData.phone"/>
    <input class="input-data"type="text" placeholder="Enter Website Here" v-model="todoData.website"/>
    <div class="d-flex justify-content-center" @click="handleCreateNewData">
        <button class="btn btn-success mt-3 d-flex btn-create">Create</button>
    </div>
  </main>
</template>

<style>
.input-data {
    margin-top: 1rem;
}
.btn-create{
    float: right;
}
</style>