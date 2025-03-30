<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <div class="container">
        <header>
        <div class="myLogo d-flex align-items-center text-success">
            <img class="logo" width="60" height="60" src="@/assets/logo.svg" alt="Vue logo">
            <nav class="h2">Huy Pham</nav>
        </div>
        <nav>
            <RouterLink to="/">
                <div class="btn-main">Home</div>
            </RouterLink>
            <RouterLink to="create">
                <div class="btn-action">Create</div>
            </RouterLink>
        </nav>
    </header>
    </div>

    <RouterView></RouterView>
</template>

<style scoped>
/** .container {
    display: flex;
    flex-direction: column; 
    justify-content: center; 
    align-items: center; 

    margin: 0 auto; 
    padding: 20px; 
    box-sizing: border-box;
}*/
a {
  text-decoration: none;
  color: #fff;
}
</style>
