<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <div class="container">
        <header>
        <img class="logo" width="60" height="60" src="@/assets/logo.svg" alt="Vue logo">
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
header {
    display: flex;
    justify-content: space-between;
    padding: .4rem 2rem;
    align-items: center;
    box-shadow: 0px 5px 5px rgba(0, 0, 0, 0.15);
    border-left: transparent;
}
nav {
    display: flex;

}
a {
  text-decoration: none;
}
</style>
