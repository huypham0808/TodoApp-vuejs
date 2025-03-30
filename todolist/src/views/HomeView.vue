<script setup>
import { computed, onMounted, ref } from 'vue';
import { useRouter } from 'vue-router';

const users = ref([]);
const txtSearch = ref('');
const router = useRouter();

onMounted(() => {
  //Su dung asyn await
  (async () => {
    const res = await fetch('https://jsonplaceholder.typicode.com/users');
    const data = await res.json();
    users.value = data;
  })(); //Dau () dau tien la function, dau () thu 2 se thuc thi function => day la cach khai bao nhanh

  // fetch('https://jsonplaceholder.typicode.com/users')
  //     .then(response => response.json())
  //     .then(json => users.value = json)
});

const filterUser = computed(() => {
  return users.value.filter(item => item.name.toUpperCase().indexOf(txtSearch.value.toUpperCase()) !== -1 || item.email.toUpperCase().indexOf(txtSearch.value.toUpperCase()) !== -1)
});
</script>

<template>
  <main class="container" style="padding-top: 2rem;">
    <input type="text" placeholder="Enter Search Here" v-model="txtSearch"/>
    <div class="row justify-content-center " >
        <div class="col-md-4 card card-item w-25 m-3" v-for="user in filterUser">
          <div class="card-body" @click="router.push({path:`/todo/${user?.id}`})">
            <h4 class="card-title">{{user?.name}}</h4>
            <i>{{user?.email}}</i>
          </div>
        </div>    
    </div> 
  </main>
</template>

<style>
input {
  width: 100%;
  padding: .6rem 1.2rem;
  border-radius: 50px;
  border: none;
  outline: none;
  background: #ededed;
}
.card-item {
  background: #324558;
  color: #fff;
  margin-top: 1.6rem ;
  cursor: pointer;
}

.card-item:hover {
  background: #243241;
}
</style>