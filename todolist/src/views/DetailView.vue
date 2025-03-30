<script setup>
import { useRoute } from 'vue-router';

const router = useRoute();
</script>

<template>
  <main class="container">
    Todo Item {{router.params.id}}
  </main>
</template>