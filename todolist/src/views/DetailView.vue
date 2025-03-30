<script setup>
import { onMounted, ref } from 'vue';
import { useRoute } from 'vue-router';

const router = useRoute();
const user = ref(null);

onMounted(() => {
  //Su dung asyn await
  (async () => {
    const res = await fetch(`https://jsonplaceholder.typicode.com/users/${router.params.id}`);
    const data = await res.json();
    user.value = data;
  })();
});
</script>

<template>
  <main class="container">
    <!-- Todo Item {{router.params.id}} -->
     <div class="card card-item p-3">
        <h4>Name: {{ user?.name }}</h4>
        <h5>Phone: {{ user?.phone }}</h5>
        <h5>Email: {{ user?.email }}</h5>
        <h5>Address: {{ user?.address.city}}</h5>
     </div>
  </main>
</template>